# Using the zLUX sample application plug-in

Your zLUX installation provides a sample application plug-in with which you can experiment.

To build the sample application plug-in, node and npm must be included in the PATH. You can use the `npm run build` or `npm start` command to build the sample application plug-in. These commands are configured in `package.json`.

**Note:**

* If you change the source code for the sample application, you must rebuild it.
* If you want to modify `sample-app`, you must run `_npm install_` in the virtual desktop and the `sample-app/webClient`. Then, you can run `_npm run build_` in `sample-app/webClient`.
* Add an item to `sample-app`. The following figure shows an excerpt from `app.component.ts`:

  ```text
   export class AppComponent {
      items = ['a', 'b', 'c', 'd']
      title = 'app';
      helloText: string;
     serverResponseMessage: string;
  ```

* Save the changes to `app.component.ts`.
* Issue one of the following commands: 
  * To rebuild the application plug-in, issue the following command:

    ```text
    npm run build
    ```

  * To rebuild the application plug-in and wait for additional changes to `app.component.ts`, issue the following command:

    ```text
    npm start
    ```
* Reload the web page. 
* If you make changes to the sample application source code, follow these steps to rebuild the application: 1. Navigate to the `sample-app` subdirectory where you made the source code changes. 2. Issue the following command:

  ```text
        npm run build
  ```

  1. Reload the web page. 

