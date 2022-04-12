# Take home assessment

### Description

A fictional AI company has been attempting to use a large image & text dataset and needs the help of human reviewers to rank, filter, and approve of the data.

To simplify the process, they're want to make a platform where reviewers can quickly:

- View the sample's image & text
- Assign each sample a score between 1 - 5
- Edit the sample text if needed before approving/removing it
- Approve or remove the sample from the dataset

### UI 

This application should give the user both the ability to sort through samples and view an entire list of past samples. When a link to an old sample is selected, a server side generated page with the details for that sample should open in a new tab. 

Inside the sorting UI, keyboard shortcuts should allow reviewers to approve, toggle the edit feature, score, and remove samples quickly. Because mistakes are common, having an "Undo" keyboard shortcut for the last sample would be very useful.

### API

The endpoint `https://jsonplaceholder.typicode.com/photos/1` (where 1 is the index of the post) returns a JSON object that looks like this: 

`{
  "albumId": 1,
  "id": 1,
  "title": "accusamus beatae ad facilis cum similique qui sunt",
  "url": "https://via.placeholder.com/600/92c952",
  "thumbnailUrl": "https://via.placeholder.com/150/92c952"
}`

You should create a new endpoint called `request_sample` that requests this endpoint and returns a slightly different datatype to the frontend when requested: 

`{
  "id": 1,
  "text": "accusamus beatae ad facilis cum similique qui sunt",
  "image_url": "https://via.placeholder.com/600/92c952",
}`

This data should then be shown to the user to sort and should be saved on the backend when submitted. Storing the data can be as simple as writing to a JSON file or can be a proper SQLite DB.  

### Notes 

Feel free to use UI Kits like [chakra](https://chakra-ui.com/), MUI, or any other to make the bulk of the interface. Wrt the UI, we're more interested in the interface's ease of use than the aesthetic/design choices made. 

### This starter repo

This repo also contains a quick starter you can clone to get started with Typescript + Next.js. To use it, clone it, install the necessary packages, and run `npm run dev`.

If you'd prefer not to use typescript for this project or would like to use a different starter, you can go to [Next.js Examples](https://nextjs.org/examples) and get started with one of theirs.