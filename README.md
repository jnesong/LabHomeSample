## Lab Home Code Sample

### Intro 
Hi 😊 This is a code sample from my lab app's home component, which can be visited in full at https://jennychau.herokuapp.com/lab.
<br/>
The code can be viewed at https://github.com/jnesong/portfolio.
<br/>
This code is intended as an example for job applications and not designed for external use.
<br/>

### Project Purpose
> Lab App was inspired by my 4 years working as an oncology and acute care nurse. Because cancer has the horrible knack for drastically affecting multiple organs at once, people with cancer often present with a multitude of symptoms. One of the first steps in the differential diagnosis is to compare labs. Once the labs result, its up to healthcare professionals to triage the results from most critical to least and understand what the root issues are. In this process, I frequently thought it would be more efficient, and less prone to human error, to have a single page where healthcare professionals could compare the causes of abnormal lab results (rather than rely on their memory or the slow process of looking up each lab in a lab manual). To demonstrate the utility of this app, I chose 6 lab tests people may be familiar with. A challenge with this app was finding a free API of lab data, so all of the lab data is pulled from a hard copy of Mosby's Diagnostic and Laboratory Test Reference and stored in another component called LabBank. Lab App is built with React front end and Rails backend.

### Code breakdown
 <details>
  <summary> Lines 1-9 </summary>
    <p> Imports React hooks and my other components utilized through this component. Also imports the style sheet for this portion of my portfolio. </p>
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
    <p> Demonstrates the React Hook useEffect's empty dependency array to only pull the lab data for the gold labs state once, when the home component first renders. The array of gold labs can then be passed as a prop for children components to share rather than import LabBank to each component, which would also work. </p>
</details>

 <details>
  <summary> Lines 21-47 </summary>
    <p> Takes the user entered result data, which is supplied through a function that is passed down via props to the LabForm component (lines 72-75) and uses the sortEachLab function to  sort the entered labs into abnormal, normal, or unentered categories based on their user-submitted values. The normal range is determined by min and max values, found as key/value information from the gold labs array. The labs are connected as argument pairs and through IDs- hemoglobin being 0, wbc being 1, and so on (lines 40-45). The sort occurs by comparing the user entered lab value to the gold array's min and max info and then adding the corresponding lab from the gold labs array to the objects abnorm, norm, and zeros (lines 22-24) and then setting states to be passed to child components as arrays (lines 47-49). Objects are used here to prevent potential duplicate lab result entries, as objects require unique keys, so the correct/current value will replace the older value for the same lab because they share the same key. </p>
</details>

 <details>
  <summary> Lines 49-53 </summary>
    <p> Fetches all past user entered lab results from the backend database, using the /api/records GET route, which connects with my Rails backend Records controller's index action. The first repsonse is parsed from JSON to javascript and then that javascript data sets the lab history state, to be passed via props to children components. </p>
</details>

 <details>
  <summary> Lines 55-65 </summary>
    <p> The makeHistory function takes the user entered result data, which is supplied through a function that is passed down via props to the LabForm component (lines 72-75) and makes a fetch request to the /api/records POST route, which connects with my Rails backend Records controller's create action. Lines 58-60 specify the data will be sent in JSON, and the javascript data is converted to JSON in line 61. After posting the data to the backend, lines 63 and 64 returns the data, parses it back from JSON into javascript and updates the lab history data to contain the newly created data, to be passed via props to children components. </p>
</details>

 <details>
  <summary> Line 67 </summary>
    <p> Initializes and holds state for the lab form toggle which is controlled via a button in the LabToPortNav component (lines 77-80). Because the toggle button in LabToPortNav affects the display of the LabForm (lines 72-75), the state is better stored in the parent LabHome component. </p>
</details>


 <details>
  <summary> Lines 70-92 </summary>
    <p> The JSX portion returned by the component produces the React elements that are rendered onto the DOM. In this case, child components and their props which contain the more specific user interface elements. </p>
</details>

 <details>
  <summary> Line 98 </summary>
    <p> Makes the LabHome component available for import to the rest of the application. </p>
</details>


A gif of Lab App:

![lab](https://user-images.githubusercontent.com/89889344/166989301-0dfa60b7-aa4e-447b-8ccb-53ed0cad7467.gif)
