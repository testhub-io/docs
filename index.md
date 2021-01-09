Testhub is an easy way to aggregate and analyze test results. 

## Getting started 

[Get our one pager quick start](./testhub-integration.pdf)

There is not need in creating account or registering. All you need is to use one of the integration methods to start uploading test results.  
Please refer to our examples to check how it looks like: https://test-hub.io/testhub-io-examples 

⛔ Testhub makes test results available publicly. If you don't want to share this information please contact us. 

#### Github Actions
Add our Github action: https://github.com/marketplace/actions/test-results-uploader-to-test-hub-io and specify   
  ```
    test_result_pattern: "/target/surefire-reports/**/*.xml"
    test_coverage_pattern: "/target/site/jacoco/jacoco.xml"
  ```

Results will be available under `https://test-hub.io/[GITHUB_ORGANISATION]` url

#### Testhub-cli

Add testhub upload step to your build process. 
1. Download CLI: 

  - Linux https://github.com/testhub-io/testhub-cli/releases/download/v0.10/testhub-cli_v0.10_linux_386.tar.gz
  - Darwin https://github.com/testhub-io/testhub-cli/releases/download/v0.10/testhub-cli_v0.10_darwin_amd64.tar.gz
  - Windows https://github.com/testhub-io/testhub-cli/releases/download/v0.10/testhub-cli_v0.10_windows_386.tar.gz


  Install (Linux):   
  `curl https://github.com/testhub-io/testhub-cli/releases/download/v0.10/testhub-cli_v0.10_linux_386.tar.gz --output testhub-cli.tar.gz -L  && tar -xzf testhub-cli.tar.gz`    
  
2. Run

`./testhub-cli upload  -t [API_TOKEN] --build $BUILD_NAME  --project $ORG/$PROJECT_NAME --pattern $GLOB_PATTERN_FOR_TEST_FILES`
- `$BUILD_NAME` - test run name or build name. Usually a build number
- `$ORG` - organisation name, all test results will be available under this organisation name 
- `$PROJECT_NAME` - project name, usually it's is same a git  repository name 
- `$GLOB_PATTERN_FOR_TEST_FILES` - glob pattern to search for test files, like `/target/surefire-reports/**/*.xml`. 

We support JUnit but it could be easily extended you can specify the root folder where cli starts search using `-r` flag
  
Results will be available under `https://test-hub.io/[ORG]`
  
#### Docker image
If you build system support using docker images you can use our pre-build image  
- [Testhub Docker image](https://hub.docker.com/r/testhubio/cli)
refer to docker images description to see the execution parameters 


### Results 
Your test results will be available 

### Support or Contact

Contact us [thetesthubio@gmail.com](mailto:thetesthubio@gmail.com) or create an issue in [Github Issues](https://github.com/testhub-io/docs/issues)
