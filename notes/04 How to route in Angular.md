## Routing
Routing is our way of navigating between components which represent our pages.
![[Pasted image 20231209225458.png]]
![[Pasted image 20231209225536.png]]
We are going to create details component and router so that users can navigate to that new component.
First, enable routing in our application. Change the main.ts like this:
![[Pasted image 20231209234407.png]]
Create src/app/routes.ts file.
![[Pasted image 20231210004534.png]]
Add route to main.
![[Pasted image 20231210005701.png]]
Create the route for the home page. Default page route is empty.
![[Pasted image 20231210005950.png]]

In main.ts we are going to update application to use our new routes.ts route defenitions. Let's add an import to the file import list at line 4. Update provideRouter at line 8.
![[Pasted image 20231210010345.png]]

## Details component
Let's create details component.
``` Shell
ng g c details --standalone --inline-template
```

We are going to do two things:
1. Add a new route to the routes.ts file.
2. Add a link to the Details page to the housing dash list component.
![[Pasted image 20231210060507.png]]
![[Pasted image 20231210062019.png]]

Then add inject a data to details template.
![[Pasted image 20231210062454.png]]

## Recap
1. Navigated in our application using the Angular router and the routerlink directive.
2. Passed information to a router using the parameterized routes.
3. Retrieved information from a route in a component using the ActivatedRoute feature.

## Resources:
1. https://youtu.be/r5DEBMuStPw?si=98J-w3AfhtjNb9Tu