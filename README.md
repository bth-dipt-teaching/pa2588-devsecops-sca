# PA2588 DevSecOps: Playground for SCA (Software Composition Analysis)

This is part of the course DevSecOps.
You will see how to include SCA in your development process.

## Preparation

  1. Click on [**Use this template**](https://github.com/new?template_name=pa2588-devsecops-sca&template_owner=bth-dipt-teaching)
     to create a new repository in your GitHub account (don't _fork_ it), and make sure to set the visibility to "Public".
     * The GitHub actions should run automatically and be green.
  2. Create a free account on [Snyk](https://app.snyk.io/login), go to your [Account Settings](https://app.snyk.io/account), and copy your "Auth Token".
  3. In your GitHub project, go to "Settings" > "Secrets and variables" > "Actions",
     and create a Repository Secret called `SNYK_TOKEN` with your Snyk Auth Token.

## Enable SCA in your Pipeline

  4. In `.github/workflows/sca.yml`, uncomment the block labeled "Version 1" to enable Snyk.
     * After the next successful run of the GitHub actions, under GitHub's "Security Tab", you should now see "Code Scanning Alerts" being reported.
  5. In `requirements.txt`, update the version of the "requests" library to a newer version (e.g. from `2.27.0` to `2.32.2` -- or whatever Snyk suggests as a current version).
     * After the next successful run of the GitHub actions, you should now see fewer "Code Scanning Alerts" being reported.
