#A microservice deployed to AKS using Azure DevOps
- Open a new instance of Visual Studio 2022.
- Create a blank solution named "Shopping".
- Add the solution to a GitHub repository.
- Make sure Docker Desktop is installed and runnnig locally!

##Setup Shopping.Client microservice
- Add a new ASP.Net Core v6.0 Web App (Model-View-Controller) called "Shopping.Client" to the solution. Disable all optional configurations.
  - Configure for HTTPS => NO.
  - Enable Docker => NO.
  - Do not use top-level statements => NO.
- Update launchSettings.json file.
  - Set applicationUrl to use port 5001.
  - Remove all setting related to "iisSettings" and "IIS Express".
  - Just leave "Shopping.Client" profile.
- Launch the "Shopping.Client" profile and make sure the web app is running.
- Add the "Product" model into the "Models"" folder.
- Add a folder named "Data" and add the "ProductContext" class. This DbContext will have hard coded data for the moment.
- Change the Index() action method in HomeController to pass static product data from ProductContext class.
- Update Views/Home/Index.cshtml to view data passed in from the controller.
- Make sure the data is visible on the index page by running the web app again!
- Add Docker support by right-clicking on the project and Add > Docker support... Use target OS => Linux.
- Give it some time to pull .NET Core 6 base image and build app image. The "Container Tools" view in Output panel should show the progress.
- Make sure the Docker container is running on Docker Desktop at last.
- Notice that a new "Docker" profile is added to launchSettings.json file and it's also available on the menu.
- Run the web app by clicking on the Docker profile on the menu.