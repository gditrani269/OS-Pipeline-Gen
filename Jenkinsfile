        node {
          stage('holis') {
            sh "echo test 1"
          }
          stage('input ') {
            sh 'echo hola'
            script {
                 def userInput = input(
                 id: 'userInput', message: 'Enter path of test reports:?', 
                 parameters: [
                 [$class: 'TextParameterDefinition', defaultValue: 'None', description: 'Ingrese la url del repositorio', name: 'GIT_URL'],
                 [$class: 'TextParameterDefinition', defaultValue: 'None', description: 'Ingrese el nombre de la aplicacion', name: 'APP_NAME']
                ])
                echo "La URL del repo es: "+userInput['GIT_URL']
                echo "El nombre de la app es: "+userInput['APP_NAME']
                sh 'oc new-app -p APP_NAME=' + userInput['APP_NAME'] + ' -f https://github.com/gditrani269/OS-Pipeline-Gen/blob/master/Pipeline-Template.yaml'
                sh 'oc process -f https://raw.githubusercontent.com/gditrani269/OS-Pipeline-Gen/master/New-Pipeline.yaml | oc create -f -
            }
          }
        }   
