## Components
Components in Angular have three parts.
1. Typescript Component Class
2. HTML Template
3. CSS Styles
The component class written in TypeScript provides developers a place to build their application logic. Consider this to be the place where one make API calls for data or define event handlers, for example.
A component also has an HTML template. The template is where we define the user interface for the component. We can write this in the component class. If it's a small template, or for more complex templates, we can include them in their own HTML file.
The final part of the component are the styles. The Angular CLI supports authoring styles with SAS, LESS, or plain CSS. The styles we write for our components are scoped to our components. Similar to the components template, component styles can be included in line within the component class or written in their own separate file. In this course, we'll keep the styles in a separate file.

## Changing templates
Change the main template.
![[Pasted image 20231208194632.png]]

## Search bar and search results
To create a component, we'll run the following command:
``` Shell
ng generate component Home --standalone --inline-template
```
We include `--standalone` to make a standalone component. Standalone component are Angular's new component style that reduce complexity and add some other cool features.
`--inline-template` is for simple code which is inlined.

## Reference to a new component
First update app.component.ts to reference our new component.
Add a new section to main template `app-home`. And there is an error here. That's because the main application component, App Component, needs to know about our new home component. To fix this issue we'll add a new property to the component decorator metadata for app component called imports. Since we want to use home component in this template, it's a dependency now. Use import at line 2. And add a new property called imports at line 18.
![[Pasted image 20231208200002.png]]
The result should be next:
![[Pasted image 20231208200142.png]]

## Write HTML in home component
Next move is to update the template of Home Component to contain the HTML markup for the search bar and results. Update the template in line 9. Added a form and a class` results`.
![[Pasted image 20231208201132.png]]
Result is next:
![[Pasted image 20231208201310.png]]

## Make another component
Lets create another component with this line:
``` Shell
ng generate component HousingLocation --standalone --inline-template
```
Then add a dependency to our home component in app/home/home.component.ts file in line 3. And update the imports array or the component decorator at line 8. Then, in the template section of the same file, add the app-housing-location tag as a child of the results section elements at line 17. 
![[Pasted image 20231208202212.png]]
Save the changes and see result:
![[Pasted image 20231208202235.png]]

## References:
1. https://youtu.be/R0nRX8jD2D0?si=A7YNCYCOoBO49zy5