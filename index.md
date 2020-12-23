## TestHub documentation

Testhub is an easy way to aggregate and analyze test results. 


### Getting started 

There is not need in creating account or registering. All you need is to use one of the integration methods to start uploading test results. 

:warning: Testhub makes test results available publicly. If you don't want to share this information please contact us. 

#### Github Actions
Add our Github action: https://github.com/marketplace/actions/test-results-uploader-to-test-hub-io and specify   
  ```
    test_result_pattern: "/target/surefire-reports/**/*.xml"
    test_coverage_pattern: "/target/site/jacoco/jacoco.xml"
  ```

#### Testhub-cli

Add testhub upload step to your build process. 
1. Download CLI: 
  - Linux https://github.com/testhub-io/testhub-cli/releases/download/v0.10/testhub-cli_v0.10_linux_386.tar.gz
  - Darwin https://github.com/testhub-io/testhub-cli/releases/download/v0.10/testhub-cli_v0.10_darwin_amd64.tar.gz
  - Windows https://github.com/testhub-io/testhub-cli/releases/download/v0.10/testhub-cli_v0.10_windows_386.tar.gz
  
  For example: 
  'curl https://github.com/testhub-io/testhub-cli/releases/download/v0.10/testhub-cli_v0.10_linux_386.tar.gz --output testhub-cli.tar.gz -L  && tar -xzf testhub-cli.tar.gz'
2. Run
`./testhub-cli upload  -t d2c49022ac2d491bb00292fa4457ba950934bf62 --build $BUILD_NAME  --project jenkins-x/$PROJECT_NAME --pattern $GLOB_PATTERN_FOR_TEST_FILES`
`$BUILD_NAME` - test run name or build name. Usually a build number
`$PROJECT_NAME` - name of a project, for example  jx-platform
`$GLOB_PATTERN_FOR_TEST_FILES` - glob pattern to search for test files, like `/target/surefire-reports/**/*.xml`. We support JUnit but it could be easily extended
you can specifu the root folder where cli starts search using `-r` flag
  
#### Docker image
If you build system support using docker images you can use our pre-build image  
- [Testhub Docker image](https://hub.docker.com/r/testhubio/cli)
refer to docker images 


### Support or Contact

Contact us [thetesthubio@gmail.com](mailto:thetesthubio@gmail.com) or create an issue in [Github Issues](https://github.com/testhub-io/docs/issues)
