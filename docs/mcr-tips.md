---
sidebar_position: 5
---

# MCR - Tips

I was going through previous MCR's and here's what all I realized.

- There was a functionality mentioned 
- There was an UI mockup shown 
- There was data shown 

It took a while to understand the correlation between these three. 

We have to use the data and show it in the view as described. 

In order to render it in the format as shown in sample UI view, need to understand what should be used to display: 
Are there elements involved - what should be they? - is it a textbox, textarea, input, button what should be used? 
What should be flow of development? What should I create first
Get an overall flow how it should look to the user and how they will interact. 

Next, pick up something that you know should be first thing to create and Scan the UI to understand what elements it possible represents in the UI
- is it a header tag 
- is a radio button
- is it a modal 
- is it dropdown 
- is this a flexbox, grid layout 

Next Read the data to understand how will the data appear on the UI with the help of UI elements 
- okay so this name has to be shown in this UI element eg. `name of restaurant` from this `data` to be shown in `h1` header. 

**You can do a mock drill of a supposed flow and observe the the functionality**

**For in example of the review of restaurants:** 
- There should be 4 buttons - it's name will be taken from the data. 
- The button should be clicked 
- What happens when I click that button. It takes in the cuisine name and scans the total data and displays the data that matches the cuisine name 
- Then how do we match the two? `cuisine_id` in `restaurantsData`  <=> `id` in `cuisineData`
- On matching this, what do we get as data and how should we display it? 
- When you get this data do we need to do anything additional on the data displayed? 
- Should it link to something else eg - `restaurant reviews`, if else where do we display it and what do we display? 
- Then deep diving the linked page format. 
- What data should come in the linked page? 

If we go in a supposedly hypothetical flow, we are to get some idea on how to develop and what to improve. 
At each stage we can try to understand what took me time and how do I improve it there. 

What part took time to come to the solution, that needs some introspection. 
First thing is, to understand what slows you down. 
Second thing is, to understand what can help you improve that part.
Third is obviously practicing the flow to understand how things work together. 

## Other notes 
- Code modularity 
- Remove console.logs 

UI
- Sometimes card sizes are distorted 
- Image aspect ratio is distorted 
- What to do: Try to have uniformity in card size, element size  

Data 
- Always in a separate data file instead of hard coding means putting it directly in components, get it from a file and display it. 

Functioning
- Search can have what do you want to filter with. Either in placeholder or explicitly mentioned. 
- Functionality where all to be available on different pages. Meaning is wishlist or favoriting available on all pages or only some pages, should that data be available to view or interact on some or all pages? Like if an item is wishlishted should that thing be shown on some pages and some pages we can also remove from wishlist. 


**What to avoid?** 
- Do not use inline CSS in MCR. 
- Names of files inconsistency in casing; smallcase somewhere and PascalCase somewhere. Name Component with PascalCase. 
- Keep your internal imports - organize imports. Use source action.  

**What to do**
- CSB Ready or Setup Ready in VS Code 
- Write comments for your code. One liner for functions atleast. 
- Web Storage code, JSON methods - have the syntax written somewhere also for the most common elements' syntax.
- API usage - learn to do practice that. Keep syntax handy. 
- Keep some database ready - random images - e.g. Cloudinary data uploaded in a particular size and then copy links for it.  
- Have some modules on CSS or have your own component library - with color combinations. 
- Have buttons with some basic colors ready 

**Resources**
- Free images or placeholder images: Pixabay, Lorem Pics. 