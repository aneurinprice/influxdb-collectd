podTemplate(yaml: """
apiVersion: v1
kind: Pod
metadata:
  labels:
    project: influxdb-collectd-builder
spec:
  containers:
  - name: influxdb-collectd-builder
    image: docker:dind
    command:
    - cat
    tty: true
    volueMounts:
      - name: DockerSocket
        mountPath: /var/run/docker.sock
  volumes:
    - name: DockerSocket
      hostPath:
        path: /var/run/docker.sock
"""
)

{
    node(influxdb-collectd-builder) {
      container('influxdb-collectd-builder') {
        sh "docker build -t test ."
      }
    }
}
