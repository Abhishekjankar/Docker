pipeline {


     agent {
          label "
     }

       environment {
           REPO_URL = "https://github.com/Abhishekjankar/Docker.git"
}

  stages {
  
        stage("workspace clean"){

           steps {

               cleanWs()
}

}

        stage("clone 2026Q1"){


            steps{
                dir("/mnt/Q1"){
                   git branch: "2026Q1", url:"${REPO_URL}"

}


}


}     

       stage("clone 2026Q2"){

             steps{
                dir("/mnt/Q2"){

                     git branch: "2026Q2", url:"${REPO_URL}"
}

}

}



       stage("clone 2026Q3"){
             steps{


            dir("/mnt/Q3"){

                  git branch: "2026Q3", url:"${REPO_URL}"
}
}
            


}



    stage("deploy 2026Q1 on c1"){
         agent {
          label  "slave-1"
         }
    steps{
             sh'''

                docker rm -f c1 || true
                docker run -dp 80:80 --name c1 httpd
               docker cp /mnt/Q1/index.html c1:/usr/local/apache2/htdocs/
               docker exec c1 chmod -R 777 /usr/local/apache2/htdocs/index.html
              
             '''



}


}


   stage("deploy 2026Q2 on c2"){

     steps{

       sh'''
 
               docker rm -f c2 || true
               docker run -dp 90:80 --name c2 httpd
               docker cp /mnt/Q2/index.html c2:/usr/local/apache2/htdocs/
               docker exec c2 chmod -R 777 /usr/local/apache2/htdocs/index.html
                '''

}

}

       stage("deploy 2026Q3 on c3"){
               steps{

            sh'''

               docker rm -f c3 || true
               docker run -dp 8081:80 --name c3 httpd
               docker cp /mnt/Q3/index.html c3:/usr/local/apache2/htdocs/
               docker exec c3 chmod -R 777 /usr/local/apache2/htdocs/index.html
                '''


}


}
    

}








}



