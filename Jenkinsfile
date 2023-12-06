pipeline
{
    agent
    {
        label
        {
            label "slave1"
        }
    }
    stages
    {
        stage("Branch 2023-Q1 Cloning")
        {
            steps
            {
                sh "rm -rf *"
                sh "git clone https://github.com/aniket28022001/Aniket_Wale_1st_July.git -b 2023-Q1"
                sh "sudo chmod -R 777 /mnt"
            }
        }
        stage("Installation Httpd")
        {
            steps
            {
                sh "sudo yum install httpd -y"
                sh "sudo service httpd start"
                sh "sudo chkconfig httpd on"
            }
        }
        stage("Deploying")
        {
            steps
            {
                sh "sudo cp -r Aniket_Wale_1st_July/index.html /var/www/html/"
                sh "sudo chmod -R 777 /var/www/html/index.html"
            }
        }
        stage("On SLAVE 2 Machine")
        {
            agent
            {
                label
                {
                    label "slave2"
                }
                
            }
            steps
            {
                sh "rm -rf *"
                sh "git clone https://github.com/aniket28022001/Aniket_Wale_1st_July.git -b 2023-Q2"
                sh "sudo chmod -R 777 /mnt"
                sh "sudo yum install httpd -y"
                sh "sudo service httpd start"
                sh "sudo chkconfig httpd on"
                sh "sudo cp -r Aniket_Wale_1st_July/index.html /var/www/html/"
                sh "sudo chmod -R 777 /var/www/html/index.html"
            }
    
            
        }
    }
}





