podTemplate(
    name: 'influxdb-builder',
    label: 'influxdb-builder',
    containers: [
        containerTemplate(name: 'influxdb-builder', image: 'docker:dind', resourceLimitCpu: '2048m', resourceLimitMemory: '2048Mi', resourceRequestCpu: '2048m', resourceRequestMemory: '2048Mi'),
    ],
    volumes: [
        hostPathVolume(mountPath: '/var/run/docker.sock',
        hostPath: '/var/run/docker.sock'),
    ],
)
{
//node = the pod label
node('influxdb-builder'){
checkout scm
    //container = the container label
    stage('Build'){
        container('influxdb-builder'){
            // This is where we build our code.
	    sh "pwd ; ls -l ; docker build -t test ."
        }
    }
}
}
