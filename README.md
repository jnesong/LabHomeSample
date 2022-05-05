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




![lab](https://user-images.githubusercontent.com/89889344/166989301-0dfa60b7-aa4e-447b-8ccb-53ed0cad7467.gif)
