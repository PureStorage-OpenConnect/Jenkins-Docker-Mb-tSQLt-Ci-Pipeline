A SQL Server datatools projects with an associated Jenkinsfile written using the opinionated declarative syntax that implements a build pipeline that:

- Checks the project out from SCM
- Uses msbuild to build the project into a DacPac file and spins up a container to deploy the DacPac to ** in serial ** the container spun   up will use a unique name, the name of the branch suffixed by SQLLinux and a unqiue external port
- Deploys the DacPac to the container
- Performs runs some tSQLt unit tests ** in serial **
- Renders the results to Jenkins using the JUnit plugin
- Tears down the container