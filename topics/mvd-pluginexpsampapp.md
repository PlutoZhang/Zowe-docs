# Experimenting with the zLUX sample application plug-in

Your zLUX installation provides a sample application plug-in with which you can experiment.

You can use the npm run build ornpm start command to build the sample appication plug-in. These commands are configured in package.json.

**Note:** Be aware that whenver you change the source code for the sample application, you must subsequently rebuild the sample application.

1.   Try adding an item to MVDCORE/EXAMPLES/sample-app/src/app/app.component.ts. The following figure shows the unmodified contents of app.component.ts:

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

2.   Save your changes to app.component.ts. 
3.   Issue one of these commands: 
    -   npm run build to rebuild the application plug-in.
    -   npm start to rebuild the application plug-in and wait for additional changes to app.component.ts.
4.   Reload the web page. 
5.   Whenever you make changes to the sample application source code, you must subsequently rebuild the application: 
    1.   Navigate to the MVDCORE/EXAMPLES/sample-app subdirectory where you made the source code changes. 
    2.   Issue this command: npm run build 
    3.   Reload the web page. 

**Parent topic:** [Creating an application plug-in](mvd-plugincreateappplugin.md)

