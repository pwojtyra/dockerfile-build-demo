# IS demo:

oc new-project dockerfile-build-demo

oc new-app http://gitlab.lab.is/pawel/dockerfile-build-demo.git  --context-dir=dockerfile/httpd --name=myhttpdapp

oc expose service myhttpdapp

