pipeline {
    agent any
    tools {
       terraform 'terraform'
    }
    environment {
       TF_VAR_compartment_id="ocid1.compartment.oc1..aaaaaaaacll5artaarzkn3vvawq2suenjwgns5rhjgh7wwbuwtagwpa5ooba"
       TF_VAR_bucket_name="grsiexerplwd"
       TF_VAR_bucket_namespace="${bucket_name}"
    }
    parameters {
        string(name: 'bucket_name', defaultValue: '', description: 'bucket name',)
    }
    stages {
        stage('terraform Init') {
            steps{
                sh 'terraform init'
            }
        }
        stage('terraform plan') {
            steps{
                sh 'terraform plan'
            }
        }
    }  
}
