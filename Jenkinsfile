podTemplate(
    name: 'influxdb-builder',
    label: 'influxdb-builder',
    containers: [
        containerTemplate(name: 'influxdb-builder', image: 'docker:dind'),
//        containerTemplate(name: 'influxdb-builder', image: 'docker:dind', resourceLimitCpu: '1024m', resourceLimitMemory: '1024Mi'),
    ],
    volumes: [
        hostPathVolume(mountPath: '/var/run/docker.sock',
        hostPath: '/var/run/docker.sock'),
    ],
)
    {
        //node = the pod label
        node('influxdb-builder'){
            //container = the container label
            stage('Build'){
                container('influxdb-builder'){
                    // This is where we build our code.
		    sh "docker build -t test ."
                }
            }
        }
    }
