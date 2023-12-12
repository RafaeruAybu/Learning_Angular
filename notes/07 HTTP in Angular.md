Right now, the application retrieves data from a hardcoded array in the housing service. Now, to make our app a little bit more realistic, we can add support to make HTTP requests for the housing locations. First change we would make is moving the data from a hardcoded array in our application into our standalone server on local machine that we can use to make HTTP requests.

Install a server.
``` Shell
npm install -g json-server
```

Create a config file.
``` Shell
touch db.json
```
Populate the json file with data.

Run following command to execute server.
``` Shell
json-server --watch db.json
```

Remove the data from housing service. Add the `url`.
![[Pasted image 20231212070851.png]]

In the get AllHousingLocations function, we need to make a call to the API endpoint to retrieve this data.
Update the method signature (line 12). We are going to use Fetch API to request data.
![[Pasted image 20231212071324.png]]

There's a few things to note here. We're wrapping the fetch call in a service which could seem like adding some complexity here. In this application, we only make this call once. But in other applications, we may reuse this same call in multiple places. Also, this gives us the added benefit of testability. We can provide a mock implementation of the service in our test that can return some data. To keep things simple, we're using the browser Fetch API. For more complex examples, Angular provides the HTTP client service class, so you can use that. And to find out more, head over to Angular.io.

Update other function.
![[Pasted image 20231212072101.png]]

At this point, we've changed the implementation of the service. But now we have to update the calls to this service from the other parts of the application. In home.component.ts we're going to update the constructor method to call the new promise-based service. Remove the existing code in the body of the function.
![[Pasted image 20231212072717.png]]

Finally, we'll update details.component.ts.
![[Pasted image 20231212073157.png]]

## Search bar
Open home.component.ts. We need to retrieve the data from the filter in the template for this component. We could use form group and typed forms, but that might be more than we need for this task. Instead, we'll use something called a template variable. This will allow us to get reference to an element in the template and use it in our application. Update the input element and add an attribute of the format `#filter`. The hashtag syntax creates our template variable. In this example, the variable is called filter. Let's update the button element and add a click handler. Value is a property on the input HTML element.
![[Pasted image 20231212074730.png]]

Change this to locationList to filteredLocationList:
![[Pasted image 20231212075113.png]]

Update code to use filteredLocationList:
![[Pasted image 20231212075154.png]]

## Recap
1. We used fetch to make an HTTP request to a live endpoint using json-server
2. Refactored the housing service to use promisees and async code
3. Added filtering capabilities to our app with template variables and typescript

## Resources:
1. https://youtu.be/5K10oYJ5Y-E?si=wK-fDaqIbqOGjGWO