---
sidebar_position: 1
---


# Deployment - things to consider.

In this document, we will consider the common cases to consider while deployment and how to fix them.

## 1\. Page not found error

Add a redirect file to avoid this screen/error.

![pagenotfECopy](https://user-images.githubusercontent.com/90078330/252403535-7f8942b8-4a57-46fa-8867-2da2858721fb.png)

Here's the `_redirects` file to be added. Add it in the `public` folder.

![image](https://user-images.githubusercontent.com/90078330/252403826-e348940d-49f0-4dd3-94b8-d9dbf835a712.png)

This issue where reloading individual pages in your hosted application results in a "page not found" error.

To solve this problem, you can add a `_redirects` file to the `public` folder of your application. Inside the `_redirects` file, you can add a rule that redirects all requests to the `index.html` file, which is the main entry point of your application. This will ensure that any request, regardless of the URL, will be directed to the `index.html` file.

Here's an example of the rule you can add to the `_redirects` file:

`/* /index.html 200`

By redeploying your application with this `_redirects` file in place, the issue of "page not found" after reloading should be resolved. The redirect rule ensures that all requests are handled by the `index.html` file, allowing your application to function correctly even when reloading individual pages.

Remember to check your hosting platform's documentation to ensure that it supports using a `_redirects` file for URL routing.

---

## 2\. Module not Found Error

**The error is mentioned in line 135**

![modulenotFoundErrorCopy](https://user-images.githubusercontent.com/90078330/252405468-6078737f-0d07-4fca-81aa-724689e33fa6.png)

**For module not found error on Netlify**

In this case, it says `miragejs` is missing. Upon checking `package.json` we can confirm that this is correct.

![image](https://user-images.githubusercontent.com/90078330/252407769-f667f0b7-3caf-4d0b-abc0-04f9cbb6d6d9.png)

We can see that the `miragejs` module is not there and instead another module `mirage.js` is present. This is causing issues in detecting at the time of build. Note that sometimes for some reason, this issue won't be seen locally as the module might be used in your local machine from some other folder, so even though your project runs locally, it does not mean that the project can run during `build` time, the project will run with the help of dependencies provided in `package.json`. If there are no dependencies needed mentioned they won't be installed and so the corresponding code won't run which needs this module for it to run.

Always look out and read the module not found error log carefully. Check the path mentioned and see if that file or folder exists in your GitHub repository.

* If it mentions a package name - check the `package.json` file to see if the module is part of it.
    
* If a file doesn't exist, add the file in GitHub and it will resolve the error.
    
* Sometimes you make a case change such as you change from `home` to `Home` and that can also cause module not found error.
    

Check for the name it shows on what is not found and check your code if it exists, or if there is a name mismatch seen because of case change.

Example: Here you can see the file name mentioned. It says that in line 71: Could not load `/src/frontend/components/userPosts` imported by `src/frontend/pages/userProfile/UserProfile.jsx` further it says no such file or directory.

![image](https://user-images.githubusercontent.com/90078330/252410449-44a971f9-0155-4008-8ee7-cb08680d445d.png)

Let's see what our repo has,

![image](https://user-images.githubusercontent.com/90078330/252411226-9c4f207d-5f24-4865-8d79-8af4995e3ce6.png)

![image](https://user-images.githubusercontent.com/90078330/252411294-29f3a12a-f562-4dbe-a8de-8aa2c838a15b.png)

As the error message says the import line is searching for `userPosts.jsx` but you can see that the file does not exist in that folder in the same casing. -- it is changed to `UserPosts.jsx` .

This error can be solved by their changing the casing in the import statement to what is the casing in the file, that is in `import` statement change it to `UserPosts.jsx` or create another file with `userPosts.jsx` and content same as `UserPosts.jsx`. and the `build` will resolve the error, as it will find the appropriate file for the same.

another example where the build failed:

![image](https://user-images.githubusercontent.com/90078330/252412925-e17dd739-6c6f-45d3-8f4a-2104034436de.png)

In general, If perhaps you think the file folder exists, check the name casing, `Cart` and `cart` is different for deploys but GitHub may not recognize this as a change. Just make sure in that case, whatever module/file/directory it is showing as missing add folder/file/directory for that with the case sensitivity it is displaying - for eg if the build is looking for `Cart` and if your repo has `cart`, just add `Cart` in your GitHub repo with all the files in `cart`. This should direct the build to take files from the correct folder.

If you like to read more check here: https://stackoverflow.com/q/17683458/21615561

**An experiment I tried to reproduce this issue was:**

I change the folder name from `Home` to `home` and it did not show up in the changes to be staged for commit. You can try. Try changing name from `home` to `Home` and see if it shows up in the changes to be staged. You made the change in case, but it was not acknowledged as a change to be tracked.

Same I changed the filename from `about.html` to `About.html` and it did not show any changes to be staged!

![image](https://user-images.githubusercontent.com/90078330/252416521-8470636b-0015-489a-9b98-bde5dee4b51d.png)

![image](https://user-images.githubusercontent.com/90078330/252416542-0b04e46d-e801-4dd2-ab55-766622551972.png)

It works on YOUR system but won't work if you commit again after making these changes and then deploy immediately. For the GitHub repository since it is merely storing your code as tracked and it doesn't track the `case` change, you won't figure out this issue until deployment, which is when the changes on your local system won't be present as you expect - there won't be case changes on GitHub.

So if you change name after committing and it is simply a case change that is `cart` to `Cart`, make sure to check the repo on [Github.com](http://Github.com) if the changes are reflected, and if not, change it in [Github.com](http://Github.com) and pull the changes to your system or, if you don't want to do it immediately, then remember to do it at time of deployment.

---

## 3\. For CI errors on Netlify

![image](https://user-images.githubusercontent.com/90078330/252412212-399faa90-d8d5-4642-bfeb-26eb64034421.png)

* This generally happens because there are warnings shown in local deployments but still our project may seem to run perfectly well, however in `build`, these warnings are looked at as errors and it will cause build to fail. By setting `CI` to `false`, we are letting Netlify know to ignore these errors. You can read lines 93 and 94 where it specifies this.
    

**What to do:** If your local deployment shows warnings and if your code is working fine and even then, the build is failing if this is the case, then simply `add a new environment variable` named `CI` ( C and I both in the capital ) and add its value as `false`.

![image](https://user-images.githubusercontent.com/90078330/252413046-ab2fd41a-9d27-4c86-a227-b6cba1df6b09.png)

After adding the variable you should try to `clear cache and deploy site` again.

![image](https://user-images.githubusercontent.com/90078330/252413215-fd7f5036-3bc5-4370-b3d2-5602b0de4f7d.png)

---

## 4\. Sub directory

It may happen that when you deploy your site, your repo looks like this

![image](https://user-images.githubusercontent.com/90078330/252413792-110756e1-8842-4bdb-8e24-b7acba0ff2d7.png)

Here your actual app code is in `my-app` directory. As such when you try to deploy using this repo you may face issues during `build`.

To avoid errors during `build` try this,

When you deploy your site for the first time, you will see this:

![image](https://user-images.githubusercontent.com/90078330/252414504-01749413-e2eb-4ee6-8352-d5f0e06a8f28.png)

Here in the `base directory` simply specify `my-app` which tells Netlify that your code is in this directory.

![image](https://user-images.githubusercontent.com/90078330/252414916-cf60a34f-ee8b-4ba9-817d-30b8a2719bfb.png)

---