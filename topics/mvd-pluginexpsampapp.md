# Using the zLUX sample application plug-in

Your zLUX installation provides a sample application plug-in with which you can experiment.

To build the sample application plug-in, node and npm must be included in the PATH. You can use the `npm run build` or `npm start` command to build the sample application plug-in. These commands are configured in `package.json`.

**Note:** 

- Be aware that whenever you change the source code for the sample application, you must rebuild it.

- If you want to modify `sample-app`, you must run `_npm install_` in the virtual desktop and the `sample-app/webClient`. Then, you can run `_npm run build_` in `sample-app/webClient`.

1.   Add an item to `sample-app`. The following figure shows the unmodified contents of `app.component.ts`:

     ```
       import { Component } from '@angular/core';
      
       @Component({
          selector: 'app-root',
          templateUrl: './app.component.html',
          styleUrls: ['./app.component.css']
        })
        export class AppComponent {
          items = ['a', 'b', 'c', 'd']
          title = 'app';
      }
        ```

2.   Save the changes to `app.component.ts`. 
3.   Issue one of the following commands: 
     -   To rebuild the application plug-in, issue the following command:
     ```
        npm run build
     ```
     -   To rebuild the application plug-in and wait for additional changes to `app.component.ts`, issue the following command:
     ```
       npm start
     ``` 
4.   Reload the web page. 
5.   If you make changes to the sample application source code, follow these steps to rebuild the application: 
     1. Navigate to the `sample-app` subdirectory where you made the source code changes. 
     2. Issue the following command:
          ```
           npm run build
          ``` 

     3.   Reload the web page. 



