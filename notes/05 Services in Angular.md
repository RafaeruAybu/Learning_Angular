## Service and Dependency
Here we are going to make housing location data available in details. We're going to solve this with a concept called a service. So let's start by creating a service using the Angular CLI.
``` Shell
ng g s housing
```

A service is a TypeScript class in Angular. We need to move the data from the home component to the service. Let's import the HousingLocation at line 2. Next, add a protected property to the HousingService class. at line 8. We need to populate data from the home component. So in home.component.ts copy the contents of array and place it to housing.service.ts (line 9).
![[Pasted image 20231212023047.png]]

To request data from housing.service we add a function `getAllHousingLoctaion()` to the line 112.
![[Pasted image 20231212023334.png]]

The next method is `getHousingLocationById()` at line 116.
![[Pasted image 20231212023701.png]]

## Inject to home component
Let's update our home component. Add inject in line 1, and import HousingService at line 5.
![[Pasted image 20231212023944.png]]

Then update our housing component's HomeComponent class. Delete all hard coded data in housingLocationList. Add a new parameter `housingService` at line 27. Add a new constructor with populating data from home service at line 29.
![[Pasted image 20231212024525.png]]

## Why do we use inject?
Angular uses a concept called dependency injection to allow components and other parts of the code to ask the framework for things that are needed to function, also known as dependencies. At first, this might seem like an extra step, but it gives us some great benefits:
1. It allows us to have **testable code**.
2. We can have more **reusable code**.
3. We benefit from **maintainable code**.

## Get details page functioning properly
In details component let's import housing service at line 4. Import HousingLocation interface at line 5.
![[Pasted image 20231212025444.png]]

Let's add a reference to the service by adding a property to the Component class at line 20.
Add a `housingLocation` at line 21. Refactor constructor.
![[Pasted image 20231212030059.png]]
Then update a template at line 13. In this case, we have to guard against calling dot id on undefined. So we use the optional chaining operator from TypeScript. If the housingLocation is undefined, the id property won't be accessed, and we don't have to worry about an error here.
![[Pasted image 20231212030359.png]]

## Details template
Now we've reached the point where we can finally create the details component template.
Let's update the template.
![[Pasted image 20231212031721.png]]
The result is:
![[Pasted image 20231212031743.png]]

## Recap
1. Learned how to create a service
2. Learned how to use dependency injection in components
3. Completed details page

## Resources:
1. https://youtu.be/-jRxG84AzCI?si=QUu38Z7kuvHToHY8