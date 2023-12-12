In this session we're going to add an application form and provide users of scaffolding to apply for a housing location.

## Froms
Forms allow users to input data into a web application. Forms have controls such as buttons check boxes and input fields.
In details component import forms at line 6.
![[Pasted image 20231212055422.png]]

Reactive forms module will give us access to some template features for forms. Add a decorative metadata in line 11.
![[Pasted image 20231212055624.png]]

We've configured our component to use forms the next step is to define that form module. Add a property  to the details component class called apply form camel case. And set the value equal to a new instance of form group. A form group represents a collection of form controls that make up the form. In our case we have three data points that will represent as form controls.
![[Pasted image 20231212060255.png]]

We will update the template properly of the component decorative metadata.
![[Pasted image 20231212061527.png]]

## Event binding
Let's configure our application to take an action when button is clicked. Add a submit rule in line 29.
![[Pasted image 20231212062210.png]]

Let's define `submitApplication()` at line 60.
![[Pasted image 20231212062656.png]]

What do thous double question marks even mean? Those are the knowledge coalescing operator. If the value on the left hand side is null or undefined then the value on the right hand side is used.

## Service side implementation
In `housing.service.ts`. Write the next:
![[Pasted image 20231212063815.png]]
The result is printed in logs.

## Recap
1. Learned about Angular forms, formGroup, and formControl
2. Learned to bind a formGroup to an HTML form in a template
3. Learned how to use event binding in Angular

## Resources:
1. https://youtu.be/kWbk-dOJaNQ?si=jMCfuqB_KgwCTD0b