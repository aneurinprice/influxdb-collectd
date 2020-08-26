podTemplate(yaml: """
apiVersion: v1
kind: Pod
label: influxdb
spec:
  containers:
  - name: influxdb-collectd-builder
    image: docker:dind
    command:
    - cat
    tty: true
    volumeMounts:
      - name: DockerSocket
        mountPath: /var/run/docker.sock
  volumes:
    - name: DockerSocket
      hostPath:
        path: /var/run/docker.sock
"""
)

{
    node(influxdb) {
      container('influxdb-collectd-builder') {
        sh "docker build -t test ."
      }
    }
}
