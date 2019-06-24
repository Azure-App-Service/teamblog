# Change
The base docker image used by these node images are changing from alpine to debian-stretch.
This change was made to ensure that the base images used by the build image (Image used for the build of the app on a deployment) and the runtime are the same, to avoid unexpected errors post build due to different in the build environment and the runtime environment.

# Potential impact
We do not expect apps execution to break due to this change. However, for those customers who use a bash/shell script as the startupScript, there could be potential compatibility issues.
One such example is alpine images require a different package manager compared to debian. We recommend that these customers review their startup script and verify that the startup script can execute in both alpine and stretch environments to avoid runtime issues.

# Impacted Versions:
Node 8.11, 8.12, 9.4, 10.1, 10.10, 10.14


# How can this be tested?
The West Central US region is upgraded with the above change. This is a good candidate region to deploy and test the app. Alternatively, you can download our latest images and test your app’s runtime locally. The latest image tags are available at https://github.com/Azure-App-Service/teamblog/blob/master/docs/Images.md.

We are hopeful that this set of changes will ensure a better experience for our customers on App Service Linux.

# How can I file an issue?
Open an issue in https://github.com/azure-app-service/teamblog/issues for any issues encountered on this regard.

 
Thanks,
App Service Linux team,
Microsoft.
