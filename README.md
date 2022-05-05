## Lab Home Code Sample

### Intro 
Hi 😊 This is a code sample from my lab application's home component, which can be visited in full at https://jennychau.herokuapp.com/lab.
The code can be viewed in full at https://github.com/jnesong/portfolio.
This code is intended as an example for job applications and not designed for external use.

### Project Purpose
Lab App was inspired by my 4 years working as an oncology and acute care nurse. Because cancer has the horrible knack for drastically affecting multiple organs at once, people with cancer often present with a multitude of symptoms. One of the first steps in the differential diagnosis is to compare labs. Once the labs result, its up to healthcare professionals to triage the results from most critical to least and understand what the root issues are. In this process, I frequently thought it would be more efficient, and less prone to human error, to have a single page where healthcare professionals could compare the causes of abnormal lab results (rather than rely on their memory or the slow process of looking up each lab in a lab manual). To demonstrate the utility of this app, I chose 6 lab tests people may be familiar with. A challenge with this app was finding a free API of lab data, so all of the lab data is pulled from a hard copy of Mosby's Diagnostic and Laboratory Test Reference and stored in another component called LabBank. Lab App is built with React front end and Rails backend.

### Code breakdown
 <details>
  <summary> Lines 1-9 </summary>
    <p> Imports React hooks and my other components utilized through this component and its children. </p>
</details>

 <details>
  <summary> Line 11 </summary>
    <p> Declares function component as LabHome. </p>
</details>

 <details>
  <summary> Lines 13-17 </summary>
    <p> Initializes state for data the user dynamically interacts with through the React Hook useState. </p>
</details>

 <details>
  <summary> Line 19 </summary>
    <p> Demonstrates the useEffect's dependency array to only pull the data for gold labs once, when the home component first renders. The array of gold labs can then be passed as a prop for children components to share. </p>
</details>

 <details>
  <summary> Lines 21-50 </summary>
    <p> Takes the result data, which supplied through a function that is passed down via props to LabForm (line 76) and uses the sortEachLab function to  sort the entered labs into abnormal, normal, or unentered categories based on their min and max. The min and max values are key/value information from the gold labs. The labs are connected as argument pairs and through IDs, hemoglobin being 0, wbc being 1, and so on (lines 40-45). The sort occurs by adding the lab from the gold labs array to the objects abnorm, norm, and zeroes (lines 22-24) and lastly set into state to be passed to child components as arrays (lines 47-49). Objects are used here to prevent duplicate labs result entries, as objects require unique keys, so the following value will replace the older value for the same lab because they share a key. </p>
</details>




![lab](https://user-images.githubusercontent.com/89889344/166989301-0dfa60b7-aa4e-447b-8ccb-53ed0cad7467.gif)
