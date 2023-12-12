## Next step
1. Build out the structure for the Housing component
2. Make the Housing component customizable
3. Dynamically display the housing location
4. Add CSS styling to the application

## Update housing-location
Lets update the housing-location.ts template at line 9.
![[Pasted image 20231208203349.png]]
The browser will be updated but we'll likely not find any new content. And that's because right now, the HTML doesn't have any content. The content that we need are the specific properties that make a housing location unique.
We've created three elements in the template:
1. A place for the listing photo
2. The listing heading text
3. The listing location
It will be great to be able to pass data to this component that contained the values that we need. Fortunately, these is a feature in Angular that allows us to doo just that input properties. Angular components can receive data through a feature called input properties.
![[Pasted image 20231208203916.png]]

## Interface
Now the next question is, how should that data be configured?
![[Pasted image 20231208204008.png]]
We want our components to accept housing location data in this specific format. Now, this is a job for a type. Types help us to know what to expect from data that we encounter. We can create a new type that represents our data. We'll create an interface to use in our application. Interface is a contract between us and the data. The interface tells us that we can expect the data to follow the structure defined by interface.
Lets create an interface:
``` Shell
ng generate interface housingLocation
```
Interface `HousingLocation` created in file `housing-location.ts`
Now we have the pieces to put everything together. We'll use input properties to pass data into our component and use the interface to let the component know what type of data to expect. You can mark a component property with the input decorator, and this tells Angular that the property can be set in a template. In `housing-location.component.ts` we need to update the imports to include input from Angular/core at line 1. We also need to import HousingLocation wrapped in curly braces at line 3. Next in the body of the Housing locationComponent we'll add a new property called `housingLocation` at line 19. We want to prefix the housingLocation property with the input decorator to make it an input property. The exclamation point is called the non-null assertion operator. And it tells TypeScript compiler that the value of this property won't be null or undefined.
The image tag needs a source attribute to display an image. Let's add one (line 11).
![[Pasted image 20231209210732.png]]
Property binding allows us to tell Angular that the value in quotes should be an actual property from the component class. To enable the property attribute we'll wrap the source attribute in square brackets.
![[Pasted image 20231209211307.png]]
The double curly braces are used for Angular's interpolation syntax. We can use that to mix in values and expressions into strings in our templates. When this gets rendering to the screen, the value will be a sting that reads "exterior photo of ABC", or whatever the name of the housingLocation is. We can use all over the template. It's a great tool to have in our toolbox.
![[Pasted image 20231209211805.png]]
The next step is to work with the list of locations. Let's add our list. In `home.component.ts` import HousingLocation interface. And add a new component of our HomeComponent called `housingLocationList` of type `HousingLocation[]` array. Assign it to be an empty array. Lines 4 and 24.
![[Pasted image 20231209212443.png]]
Then add to the empty array hardcoded info from https://gist.github.com/MarkTechson/efe8a9d4727ef33949b78812e66db082 line 24.

## For iterate
In Angular, there's a syntax we can use to accomplish this goal. It's called the `ngFor` directive. Let's add ngFor directive to the housingLocationComponent. The next step is to pass the housingLocation data to the housing-location components using the inputs from the component. Update the app-housing-location component to include housingLocation.
![[Pasted image 20231209220340.png]]
And we can see appearance of the houses in our browser.

## CSS
Good so far. But where is the styles? Let's add them. Get all CSS styles here https://gist.github.com/MarkTechson/fa601fdc856d26b3bfa5030dae147f00
![[Pasted image 20231209223603.png]]

## Recap
1. Built the structure for the Housing component
2. Made the Housing component customizable using Input properties
3. Used the ngFor directive to iterate over the housingListLocation array
4. Added CSS styling to the application

## References:
1. https://youtu.be/eM3zi_n7lNs?si=owt8DKMeNgQyErKW