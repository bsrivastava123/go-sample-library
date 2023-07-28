##  buildFrontendPipeline.yaml
### Inputs
#### *working-directory:* 
Directory to the folder in which the app is located.
This input is *required*.

#### *building-directory*  
Directory to the folder in which the build of the app will be located after executing 'npm run build'.
This input is *required*.


#### *customize-e2e-environment:*
Directory to the folder in which a bash script is located. This is useful for those cases where some previous preparation is needed before running e2e tests.
This input is ***not** required*.

### Jobs
It executes 4 jobs:
1. Linting
2. Unit tests
3. Building
4. E2E tests
### Artifacts
1. *Unit tests:* Unit test report + Comments the PR with the coverage.
2. *Building job:*  App build.
3. *E2E:* Screenshots of those tests that failed.
## Requirements
The project should contain the following libraries installed and configured:
- eslint or any linting tool
- jest
- jest-junit
- cypress
### Jest
jest.config.js should include this coverage reporters:

     coverageReporters: ['cobertura', 'html', 'lcov']
### Package.json
Scripts to run unit tests and linting:

      "scripts": {
	    "test": "jest --coverage --ci --reporters=default --reporters=jest-junit",
	    "lint": "npx eslint src/**"
	    }





