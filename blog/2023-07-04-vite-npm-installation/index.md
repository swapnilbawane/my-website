---
slug: installvite
title: Deploy simple React App locally with Vite & NPM.
authors: [swapnil]
tags: [vite, npm]
---

## Step by step guide for installing simple React App.

**Note:** This article was also published here: [Hashnode blog](https://swapnilbawane.hashnode.dev/deploy-simple-react-app-locally-with-vite-npm)

## PART 1: Creating a basic folder structure for React Project

Open your VS Code terminal and run the following command in any folder to create a new Vite project with React support:

```plaintext
npm create vite@latest my-react-project --template react
```

![image](https://user-images.githubusercontent.com/90078330/248503667-c1bf5f50-f019-479b-b5a1-4811702442dc.png)

Replace `my-react-project` with any project name. This will be your folder name.

Then Select `React` from the below screen

![image](https://user-images.githubusercontent.com/90078330/248503766-2dd4bfa3-2bac-4d74-8b00-92604fbd7b0b.png)

Select `Javascript`

![image](https://user-images.githubusercontent.com/90078330/248503810-f4ffc3bd-e837-4a92-b535-d1b0eda481bd.png)

That's it you will see a command to proceed further:

![image](https://user-images.githubusercontent.com/90078330/248503869-3f545f89-9189-4d47-8be8-1cdba957b2a5.png)

After that, there are 2 steps:

1. Navigate to the project directory created with the name you chose earlier. Here `cd my-react-project` will navigate to the folder created.
    

![image](https://user-images.githubusercontent.com/90078330/248504022-0285df8d-5635-4804-b32c-fc0403e89986.png)

1. You now need to type `code .` that is code spacebar and dot - this will open your newly created `my-react-project` in a new window.
    

![image](https://user-images.githubusercontent.com/90078330/248504716-3f545c55-f1c6-4658-9923-ecce86ace24e.png)

---

Now we will begin. Open the terminal using Windows + backtick and install packages

![image](https://user-images.githubusercontent.com/90078330/248504941-5bfa5e49-323a-4aec-858e-637ef10bd7ca.png)

Packages will keep getting installed and you will see a progress bar.

![image](https://user-images.githubusercontent.com/90078330/248505006-92e94f9f-5014-4772-8bf9-c5d1356ac597.png)

Once you are done installing you will see the terminal free again to type. You can ignore these warnings.

![image](https://user-images.githubusercontent.com/90078330/248505084-e8917cd1-2305-406d-9626-d3e7dad1be95.png)

You can install packages you don't see installed in the `package.json` file and you require for your project using `npm install <package name>` Here I am installing `react-router` and `react-router-dom`

![image](https://user-images.githubusercontent.com/90078330/248505166-d7635415-735c-419b-9d2d-e7a2fe06c2ff.png)

Now I have installed all the required packages, So I am going to deploy this project using the `npm run dev` command. This command was displayed just after the `my-react-project` creation using the `npm` command.

![image](https://user-images.githubusercontent.com/90078330/248505314-a2cdab56-d54f-4969-9986-93afc14063c5.png)

---

Now running `npm run dev` the project is deployed and you can view it on your browser. Click on the link or type the link to see your deployed project.

![image](https://user-images.githubusercontent.com/90078330/248505384-6d4de862-b214-4555-b357-4f959f5e28d0.png)

You can see it deployed like this:

![image](https://user-images.githubusercontent.com/90078330/248505443-888f23b9-e491-4c78-bd98-f22def17c0f1.png)

---

**THIS IS PART 1** - Where we just create a basic folder structure to start our React project.

*In Part 2 - We will see git repository initialization and publishing to remote, and also about the folder structure.*

---

# PART 2: Additional work to deploying React Project: Git + Looking at folder structure.

Git repository initialization and publishing to remote on [Github.com](http://Github.com)

If we look at the terminal now, we can see that project is deployed but we can't use the same terminal, so we add a new split terminal through the below setting. This terminal will be used for Git purposes.

![splitterminal](https://user-images.githubusercontent.com/90078330/248505576-8900a9f5-540c-45cf-aa4e-7880059414ec.png)

---

We now have a split terminal ready to do our project.

![image](https://user-images.githubusercontent.com/90078330/248505879-94414789-577d-4dbb-b953-82079ecdd973.png)

The left side terminal will keep showing warnings and errors as we add more code. So use it to read the errors. If needed to check errors - you can also see this in the `console` of `Inspect browser`

The right side of the terminal should be used for git purposes.

Now what we have done is just created a local directory with just the files created by running the command. To confirm if the git repository is created or not, we will run the `git status` command.

As you can see below no repository exists, so file changes we do may not be tracked. We need to create a Git repository now.

![image](https://user-images.githubusercontent.com/90078330/248506071-473e1ee7-d75c-4765-b069-42d9c1441774.png)

To create a git repository use `git init`

This will make an empty repository for the folder.

![image](https://user-images.githubusercontent.com/90078330/248506181-6576917c-4e6c-4c58-9a46-1bc5fb859bfb.png)

Next, we need to add the files to this git repository. So we use `git add .` git add dot to add all the files created till now to the git repository just created.

![image](https://user-images.githubusercontent.com/90078330/248506249-5634c535-4675-487e-b518-c3b68ea52126.png)

Now all the files are staged, we can commit these files using Git command `git commit -m "initial setup"` This will commit the staged changes with the commit message as "initial setup.

![image](https://user-images.githubusercontent.com/90078330/248506381-36a6e99d-4ed9-4a0e-8e87-8e482140eaf6.png)

![image](https://user-images.githubusercontent.com/90078330/248506412-ba1f42f3-c49f-4ca9-93fd-22f05e144e27.png)

Now we have successfully saved all changes made till now to a git repository but the changes are there only in the local machine.

Let's connect it to the remote repository:

To connect to a remote repository - publish branch - this will prompt you to create a new repository with the same name.

![publishbranch](https://user-images.githubusercontent.com/90078330/248506582-fbf068d8-3857-44e9-97d9-fc6a6fcb7abe.png)

This will prompt you to create a GitHub repository with the same name or you can change the name also in the text box: Select either - to create a public or private repository.

![publishbranch2](https://user-images.githubusercontent.com/90078330/248506727-830a6d89-0593-4455-8cc0-fb85b4bb7e86.png)

While publishing you can see progress here:

![publishingonline](https://user-images.githubusercontent.com/90078330/248506929-732c8e38-23c5-454c-8f50-def3535397ad.png)

Once published, you can ignore the pull request notification and click on `Open on GitHub` to see the repository created.

![publishedonline](https://user-images.githubusercontent.com/90078330/248507000-5417ba0b-7668-4fc7-9439-eb63d066886d.png)

Here's the repository created online:

![image](https://user-images.githubusercontent.com/90078330/248507057-be523522-c7f0-4cc7-8bc4-9f6baa2e369e.png)

You can now visit the terminal again and type `clear` to clear the terminal of previous messages.

![image](https://user-images.githubusercontent.com/90078330/248507116-194c7b73-3e40-4fcb-87db-8d44aca1c70c.png)

**NOTE: Once the branch is published you can push the committed code to remote using** `git push origin <main/master>`

![image](https://user-images.githubusercontent.com/90078330/248539318-ee7fe4c6-3ca1-4ebd-bb04-2f3ca156a198.png)

![image](https://user-images.githubusercontent.com/90078330/248539355-dd6fa55f-3a83-428e-9fae-f254b5889a3a.png)

---

## Now let's look at the folder structure

![image](https://user-images.githubusercontent.com/90078330/248507236-cb1bb850-53c2-476d-8cb4-31d1a6c91213.png)

You can remove or edit any of the files here.

To start from scratch

* Remove CSS configurations entirely from `App.css` and `index.css`
    
* You can also entirely remove contents from `App.jsx` file
    

![image](https://user-images.githubusercontent.com/90078330/248507765-0ca7a901-7eb5-42da-ab1e-33de9f130c2e.png)

**NOTE:** If you planning to use React Router then you can also set it up. Here `main.jsx` is the file like `index.jsx` in CRA.

* Import `BrowserRouter` after making sure that `react-router` and `react-router-dom` are added in `package.json` file.
    

As you keep adding more code, the alignment of the code written may look messy. Use `Prettier` VS Code Extension and then right-click and `Format Document` If a popup comes select `Prettier` and then you can see code formatted to look cleaner in view.

![formatprettier](https://user-images.githubusercontent.com/90078330/248539725-40c478d9-fdb3-4ccc-ae80-db577ccb6c3f.png)

Wrap the `BrowserRouter` around `<App/>` and then proceed to make a `<Home/>` componet

![image](https://user-images.githubusercontent.com/90078330/248539815-83f116df-4344-440b-af22-1e236f6ac6af.png)

* You can then set up the Router in `App.jsx` with routes as `<Route path="/" element={<Home />} />` which is wrapped around `<Routes> </Routes>`
    

![image](https://user-images.githubusercontent.com/90078330/248539929-327dcdaa-0a6a-44e9-8068-e9ccb4abd025.png)

![image](https://user-images.githubusercontent.com/90078330/248539981-859ccdee-3e82-4c58-a2cc-b9be094dcfe3.png)

---

**For subsequent changes along with Ctrl + S or Autosaving on VS Code, You also need to do:**

* `git add .` ( to stage or add all files saved till now to git history )
    
* `git commit -m "<commit message>"`
    
* `git push origin <branchname>`
    

If you close the session of VS Code which has the terminal running updates from the server - the server is also stopped. If you restart VS Code again, navigate to folder and re-start the server with `npm run dev` Then use split terminal to run the git commands.

![image](https://user-images.githubusercontent.com/90078330/248539148-699bf2a7-c895-4313-8fe3-50325358305f.png)

**NOTE:** If you have deployed your React app via Github repository to Netlify, all the changes will be read and for every commit - there will be deploys on Netlify - if there are errors during development - some builds will fail. Resolve errors to deploy on Netlify / Vercel successfully.

**Make sure to import necessary packages to avoid errors. If you do not see any error during runtime and just see blank screen, you can check** `console` **in** `Inspect Browser`

PS: If you rather want to see the error on screen during local deployment, add this code in `App.jsx` file after import statements.

```javascript
import './App.css'
import { Routes, Route } from "react-router-dom"
// import { Home } from './Home'

if (import.meta.env.DEV) {
  window.onerror = (event, source, lineno, colno, err) => {
    const ErrorOverlay = customElements.get('vite-error-overlay');
    if (!ErrorOverlay) {
      return;
    }
    const overlay = new ErrorOverlay(err);
    document.body.appendChild(overlay);
  };
}
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688206430889/fb21b319-be82-405f-a41c-9884a557de64.png)

This will show error now like this:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688206509742/15a732e5-ec9e-4d2e-89d6-e844060ead32.png)

---

**Resources:**

[Getting Started | Vite (](https://vitejs.dev/guide/)[vitejs.dev](http://vitejs.dev)[)](https://vitejs.dev/guide/)

