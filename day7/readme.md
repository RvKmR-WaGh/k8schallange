## Task 7/40


1. **Task Details** ☕️

**Task 1**
- Create a pod using the imperative command and use nginx as the image:
  ```
  kubectl create pod ngnx --image=nginx:latest
  ```
- Check pod created:
  ```
  kubectl get pods
  ```


**Task2**
- Create the YAML from the nginx pod created in task:
  Two ways:
  - Create yaml/json file 
```
ravikumar@rvkmr:~/k8s/k8schallange/day7$ cat nginx.yaml 
apiVersion: v1
kind: Pod
metadata:
  labels:
    app: web
  name: nginx
spec:
  containers:
    - image: nginx:latest
      name: new-nginx
```
Export existig pod, remove un-necessary and modify contents accordning to requirements and create pod
```
ravikumar@rvkmr:~/k8s/k8schallange/day7$ kubectl get pod ngnx -o yaml >> exported_ngnx.yaml
ravikumar@rvkmr:~/k8s/k8schallange/day7$ vi exported_nginx.yaml
ravikumar@rvkmr:~/k8s/k8schallange/day7$ kubectl create -f exported_ngnx.yaml
ravikumar@rvkmr:~/k8s/k8schallange/day7$ kubectl get pods
NAME            READY   STATUS    RESTARTS   AGE
exported-ngnx   1/1     Running   0          8s
nginx           1/1     Running   0          11m
```

**Task3**
- Apply the below YAML and fix the errors, including all the commands that you run during the troubleshooting and the error message

```YAML
apiVersion: v1
kind: Pod
metadata:
  labels:
    app: test
  name: redis
spec:
  containers:
  - image: redis:latest
    name: redis
    
ravikumar@rvkmr:~/k8s/k8schallange/day7$ kubectl create -f redis.yaml 
pod/redis created
ravikumar@rvkmr:~/k8s/k8schallange/day7$ kubectl get pods
NAME    READY   STATUS    RESTARTS   AGE
nginx   1/1     Running   0          4m21s
ngnx    1/1     Running   0          7m51s
redis   1/1     Running   0          27s

```
2. **Share your learnings**: Document your key takeaways and insights in a blog post and social media update
 - [kubectl apply -f<FILE> ] command will not working untill resource is created


