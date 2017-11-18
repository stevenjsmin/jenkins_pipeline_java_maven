node {
   // Mark the code checkout 'stage'....
   stage 'Checkout'
   
   git url: 'https://github.com/stevenjsmin/jenkins_pipeline_java_maven.git'

   // Get the maven tool.
   // ** NOTE: This 'M3' maven tool must be configured
   // **       in the global configuration.           
   def mvnHome = tool 'M3'

   // Mark the code build 'stage'....
   stage 'Build'
   // Run the maven build
   sh "${mvnHome}/bin/mvn -Dmaven.test.failure.ignore clean package"
   step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml'])

    // echo "My branch is: ${BRANCH_NAME}" // --> Error
    echo "My branch is 1: ${env.BRANCH_NAME}"
    echo "My branch is 1: ${env.GIT_BRANCH}"
    echo "My branch is 1: ${GIT_BRANCH}"
    def git_branch = env.BRANCH_NAME[0]
    echo "My branch is 2: ${it_branch}"
    //echo "scm.branches[0].name : ${scm.branches[0].name}" // --> Scripts not permitted

}