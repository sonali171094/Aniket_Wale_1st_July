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
                sh "git clone https://github.com/aniket28022001/Aniket_Wale_1st_July.git -b 2023-Q1"
                sh "chmod -R 777 /mnt"
            }
        }
        stage("Installation Httpd")
        {
            steps
            {
                sh "yum install httpd -y"
                sh "service httpd start"
                sh "chkconfig httpd on"
            }
        }
        stage("Deploying")
        {
            steps
            {
                sh "cp -r Aniket_Wale_1st_July/index.html /var/www/html/"
                sh "chmod -R 777 /var/www/html/index.html"
            }
        }
        
    }
}
