pipeline{

    agent any

      environment {
           REPO_URL = "https://github.com/Abhishekjankar/Docker.git"
}


    stages {

       stage{"deploying on slave-1"){

               agent{
                    label "slave-1"
}

               stages{
                  stage("cloning branches"){
                       steps{

                         dir("Q1"){
                              git branch: "2026Q1", url:"${REPO_URL}"

}
                         dir("Q2"){
                           git branch: "2026Q2", url:"${REPO_URL}"
}

                           dir("Q3"){
                              git branch: "2026Q3", url:"${REPO_URL}"
  
}
}

}


                  stage("deploying"){
                      steps{

                          sh'''
                          
                          sudo docker rm -f c1 c2 c3 || true
                          sudo docker run -dp 8081:80 --name c1 httpd
                          sudo docker cp Q1/index.html c1:/usr/local/apache2/htdocs/
                          sudo docker exec c1 chmod -R 777 /usr/local/apache2/htdocs/index.html

                           sudo docker run -dp 8082:80 --name c2 httpd
                          sudo docker cp Q2/index.html c2:/usr/local/apache2/htdocs/
                          sudo docker exec c2 chmod -R 777 /usr/local/apache2/htdocs/index.html


                          sudo docker run -dp 8083:80 --name c3 httpd
                          sudo docker cp Q3/index.html c3:/usr/local/apache2/htdocs/
                          sudo docker exec c3 chmod -R 777 /usr/local/apache2/htdocs/index.html
 
                    '''

}

}

}

}

      stage("deploying on slave-2"){

              agent{
                    label "slave-2"
}

               stages{
                  stage("cloning branches"){
                       steps{

                         dir("Q1"){
                              git branch: "2026Q1", url:"${REPO_URL}"

}
                         dir("Q2"){
                           git branch: "2026Q2", url:"${REPO_URL}"
}

                           dir("Q3"){
                              git branch: "2026Q3", url:"${REPO_URL}"
  
}
}

}


                  stage("deploying"){
                      steps{

                          sh'''
                          
                          sudo docker rm -f c1 c2 c3 || true
                          sudo docker run -dp 8081:80 --name c1 httpd
                          sudo docker cp Q1/index.html c1:/usr/local/apache2/htdocs/
                          sudo docker exec c1 chmod -R 777 /usr/local/apache2/htdocs/index.html

                           sudo docker run -dp 8082:80 --name c2 httpd
                          sudo docker cp Q2/index.html c2:/usr/local/apache2/htdocs/
                          sudo docker exec c2 chmod -R 777 /usr/local/apache2/htdocs/index.html


                          sudo docker run -dp 8083:80 --name c3 httpd
                          sudo docker cp Q3/index.html c3:/usr/local/apache2/htdocs/
                          sudo docker exec c3 chmod -R 777 /usr/local/apache2/htdocs/index.html
 
                    '''

}

}

}



}

}






}


