# skaffold-docker-build-and-deploy

**Prerequisites:**

 * Install Docker: Make sure Docker is installed on your machine.
 * Install Skaffold: Follow the Skaffold installation guide for your operating system. https://skaffold.dev/docs/install/

***
Open a terminal and navigate to the directory where you created the sample application and the skaffold.yaml file.
Run the following command to start Skaffold in watch mode:  `skaffold dev`

Once Skaffold starts, it will build the Docker image and deploy the application to your Kubernetes cluster. You can verify the deployment by checking the status of the deployment:  `kubectl get deployments`

You should see the skaffold-example deployment listed with one replica.
To access the application, you can port-forward the container's port to your local machine:  `kubectl port-forward deployment/skaffold-example 8000:3020`

Now you can access the application by opening http://localhost:8000 in your web browser.

Make changes and observe the workflow:  
 * Skaffold is now watching for changes in your project. Try making some modifications to the **app.js** file, such as changing the response message.
 * Save the file, and Skaffold will automatically rebuild the Docker image and redeploy the application. You can observe the output in the terminal.
 * Refresh the browser window, and you should see the updated message.

