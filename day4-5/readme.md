1. **Task Details** ☕️
- Kubernet components 
  A. Control Plane:
    a. etcd
    b. api server
    c. Schedular
    d. Controller Manger
  B. Worker Node
    a. Kubelet
    b. KubeProxy(K-Porxy)
    c. Pods

- Kubernet User Request Flow:
  1. User request for pod creation
  2. API server receives request for pod creation. Request cluster state from etcd
  3. ETCD respond to api server with cluster status
  4-5. API Server, connects with schedule to schedule pod on worker node.
  6. API Server connect with kubelet on worker node and request for pod creation
  7. Kubelet connect with container run env and create pod
  8. Kubelet response to api server with cluster status
  9. api server write new cluster state back to etcd
  10. api server respond to user with pod creation


