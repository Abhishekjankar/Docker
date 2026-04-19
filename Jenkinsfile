pipeline {

agent any

stages {

stage("one"){

steps{

sh "docker cp index.html c1:/usr/local/apache2/htdocs/"
sh "docker exec c1 chmod -R 777 /usr/local/apache2/htdocs/" 
}

}




}














}
