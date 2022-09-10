pipeline {
    agent any
    tools {
       terraform 'terraform'
    }
    stages {
        stage('define variables') {
            steps{
                sh touch oci_bucket_variables.auto.tfvars
                sh echo 'compartment_id     = "ocid1.compartment.oc1..aaaaaaaacll5artaarzkn3vvawq2suenjwgns5rhjgh7wwbuwtagwpa5ooba"' >> oci_bucket_variables.auto.tfvars
                sh echo 'bucket_namespace   = "grsiexerplwd"' >> oci_bucket_variables.auto.tfvars
                sh echo 'bucket_name        = "'$bucket_name'"' >> oci_bucket_variables.auto.tfvars
            }
        }        
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
