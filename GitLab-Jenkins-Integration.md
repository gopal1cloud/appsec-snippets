### Configure Jenkins with Gitlab

> Jenkins is an open-source automation server to manage and control software delivery processes throughout the entire software development lifecycle, including build, test deployment, and much more. It's similar to Gitlab CI/CD but doesn't use YAML syntax.

Before we start with Jenkins, we need to configure it as the default CI/CD system for Gitlab. 

We can do it in __two__ steps

#### Step 1

Create a personal access token by visiting https://your_gitlab_url/-/profile/personal_access_tokens. We will use this token in the next step. 

Use `Jenkins` as the Name of the token. Ensure you check the __api__ checkbox under the __scopes__ and click on the __Create personal access token__ button to generate the token.

> Please save the generated token somewhere in a file, as it won't be shown again after this step.

#### Step 2

Log in to the Jenkins system and configure Jenkins to authorize the connection with the Gitlab machine by visiting https://your_jenkins_url/configure

Scroll down till you find the __Gitlab__ section and fill the form with the following details.

__Connection name__: `gitlab-server`

__Gitlab host URL__: `https://your_gitlab_url`

To configure the __Credentials__ field, we need to perform the following steps. 

Click the __Add__ button (it has a key symbol), then select __Jenkins__ a form will appear with a title __Jenkins Credentials Provider: Jenkins__. Choose __Gitlab API token__ from the __Kind__ dropdown and add the following values into it:

__Scope__: No change(leave it as is)

__API token__: Enter the personal access token we created in the __step 1__.

__ID__: `gitlab-api-token`

__Description__: leave it blank, as it's optional 

Click on the __Add__ button and select the __gitlab-api-token__ credentials from the Credentials dropdown. 

Once done, we will test the connection to ensure everything is working fine by clicking the __Test Connection__ button. If everything is set up correctly, you should see a __Success__ message. 

Finally, click on the __Save__ button at the bottom of the page.

We configured the Gitlab connection details in the Jenkins system. 
