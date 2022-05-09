# Deploying to ArgoCD
* Login to the ArgoCD console in your environment using `admin` and the admin password.
* Click the `New App` button in the top right hand corner.
* Give the application a name, set the project policy to default, set the sync policy to Automatic and check Prune Resources and Self Heal. Shown below:
<img width="816" alt="Screenshot 2022-05-09 at 8 33 25 am" src="https://user-images.githubusercontent.com/60354187/167361851-2303f5c0-b5fd-4450-941c-e53727a654b4.png">

* Fil out the source with a git repository url, add in the path you'd like to deploy.
* 
<img width="814" alt="Screenshot 2022-05-09 at 8 35 55 am" src="https://user-images.githubusercontent.com/60354187/167362269-520e289f-0db9-4ba2-b2de-48af75c5c396.png">

* Fil out destination details using name and select the default in-cluster value. Set the namespace to where you'd like to deploy to.

<img width="818" alt="Screenshot 2022-05-09 at 8 36 49 am" src="https://user-images.githubusercontent.com/60354187/167362403-b0316c55-88ee-4837-8efc-2b3445f237c6.png">

* Click create, even when the section at the bottom is set to directory but no helm chart is being picked up
* Once it starts creating, you can click `App Details`, in the `Parameters` section add in the overides by clicking `Edit` and `Save`:
  * gaas-rest.controller.applicationProperties.worker.image
  * gaas-rest.eureka.image
  * gaas-rest.image.repository
  * gaas-rest.sidecar.image
  * gaas-ui.image.repository
  * gaas-ui.envVariables.kaiRestAPIHost
  * gaas-ui.envVariables.reactAPIPlatform
  * gaas-ui.envVariables.reactAuthEndpoint
(The bottom 3 can be filled out later once the endpoints are known)
* This should redeploy the components.
