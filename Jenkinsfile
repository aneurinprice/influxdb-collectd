podTemplate(
    name: 'Influxdb-collectd-builder',
    label: 'jenkins-builder',
    containers: [
        containerTemplate(name: 'docker', image:'docker:dind'),
    ],
    volumes: [
        hostPathVolume(mountPath: '/var/run/docker.sock',
        hostPath: '/var/run/docker.sock',
    ],
    {
        node('jenkins-builder'){
            stage('Build'){
                container('docker'){
  		  sh "docker build -t test ."
                }
            }
        }
    })
