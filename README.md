# openshift-virtualization
OpenShift Virtualization and automation event DK april 2025



Create kubernetes credentials type in AAP

Input configuration:

---
fields:
  - id: kube_config
    type: string
    label: kubeconfig
    secret: true
    multiline: true
required:
  - kube_config

Injector configuration in yaml:

---
env:
  K8S_AUTH_KUBECONFIG: "{{ tower.filename.kubeconfig }}"
file:
  template.kubeconfig: "{{ kube_config }}"


Create a new kubernetes credential (copy your .kube/config file into it)

