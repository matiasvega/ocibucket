pipeline {
    agent any
    tools {
       terraform 'terraform'
    }
    environment {
       TF_VAR_compartment_id="ocid1.compartment.oc1..aaaaaaaacll5artaarzkn3vvawq2suenjwgns5rhjgh7wwbuwtagwpa5ooba"
       TF_VAR_bucket_name="${bucket_name}"
       TF_VAR_bucket_namespace="grsiexerplwd"
    }
    parameters {
        string(name: 'bucket_name', defaultValue: '', description: 'bucket name',)
    }
    stages {
        stage('provision bucket') {
            steps{
                sh 'terraform init'
                sh 'terraform apply --auto-approve'
            }
        }
    }  
}
