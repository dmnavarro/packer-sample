node ("base-ec2-spot-worker") {

  stage('Delete Current Workspace') {
    sh "rm -rf ${env.WORKSPACE}/*"
  }

  stage('Terraform Code Checkout') {
    checkout([$class: 'GitSCM',
        branches: [[name: "master"]],
        userRemoteConfigs: [[
            credentialsId: 'prd-private-gitlab',
            url: 'git@gitlab.usautoparts.com:platform-services/packer.git'
        ]]
    ])
  }

  stage('Building Scripts AMI') {
    dir (PROJECT_DIR) {
      sh "packer build packerfile.json"
    }
  }

}
