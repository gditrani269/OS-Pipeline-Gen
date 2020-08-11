El proposito de este repo es poder armar en Openshift un pipeline que se pueda usar para dar de alta otros pipelines.
Seria poder coontar con un pipeline generico que permita dar de alta pipelines custom indicando por ejemplo nombre y repo que estos nuevos pipelines usaran.

Pasos a seguir:
1 - oc process -f Pipeline-Template.yaml | oc create -f -
