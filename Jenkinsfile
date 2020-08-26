podTemplate(
    name: 'influxdb-builder',
    label: 'influxdb-builder',
    containers: [
        containerTemplate(name: 'influxdb-builder', image: 'm08y/test', resourceLimitCpu: '1', resourceLimitMemory: '4086Mi', resourceRequestCpu: '1', resourceRequestMemory: '2048Mi', ttyEnabled: true, command: 'cat'),
    ],
    volumes: [
        hostPathVolume(mountPath: '/var/run/docker.sock',
        hostPath: '/var/run/docker.sock'),
    ],
)
{
//node = the pod label
node('influxdb-builder'){
    stage('Build'){
            checkout scm
        container('influxdb-builder'){
	    sh "docker build -t test ."
        }
    }
}
}
