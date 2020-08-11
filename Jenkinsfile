        node {
          stage('delete prev ver') {
            sh "oc delete all --selector app=ger"
            sh "oc delete all --selector application=ger"
          }
          stage('ImageStream') {
            dir('app') {
              sh 'oc new-app -f https://raw.githubusercontent.com/gditrani269/s2i-dotnetcore-ex/master/openshift/ImageStream.yaml'
            }
          }
          stage('BuildConfig') {
            dir('app') {
              sh 'oc new-app -f https://raw.githubusercontent.com/gditrani269/s2i-dotnetcore-ex/master/openshift/BuildConfig.yaml'
              sh 'sleep 8'
              sh 'oc logs -f bc/ger'
            }
          }
        }
