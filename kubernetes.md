# Difference between Pod and Deployment?

```
Pod is a collection of containers and basic object of Kuberntes. All containers of pod lie in same node.

Not suitable for production
No rolling updates

Deployment is a kind of controller in Kubernetes.

Controllers use a Pod Template that you provide to create the Pods for which it is responsible.
Deployment creates a ReplicaSet which in turn make sure that, CurrentReplicas is always same as desiredReplicas .

Advantages :

You can rollout and rollback your changes using deployment
Monitors the state of each pod
Best suitable for production
Supports rolling updates
```

# Headless service with mysql master slave usecase

![image](https://user-images.githubusercontent.com/54719289/118477048-2c8c2180-b706-11eb-86d7-fff405db4624.png)

  >>  Statefulset : 
![image](https://user-images.githubusercontent.com/54719289/118477455-9a384d80-b706-11eb-9388-f2eee63321eb.png)

![image](https://user-images.githubusercontent.com/54719289/118477521-ab815a00-b706-11eb-8f0c-0d232320f1ce.png)
![image](https://user-images.githubusercontent.com/54719289/118477556-b50ac200-b706-11eb-8b54-3f132a087852.png)

```
In this scenario, we have written few datas in Pod1 and Pod3 but when you are going to read the data in Pod2 , the data wont be available . 
Its like data consistency. Here the problem is with ClusterIP, to avoid these kind of scenario headless service comes in . Like 
```

![image](https://user-images.githubusercontent.com/54719289/118477929-2fd3dd00-b707-11eb-91f9-01b3561c7c7d.png)

```
Why do we need to statefulset is if the pod is crashed then the next pod wont start with same naming convention. In deployement, the suffix of podname 
is always ends with aphanumeric but in statefulset , the pod name ends with ordinal index like mysql-0,mysql-1 like that.

Lets assume I have 3 replicas for mysql, here we will consider mysql-0 as primary  in headless service and remaining 2 pods 
are replicas of primary database mysql-0 . Whenever i write the data is mysql-0 ,i will take a backup and execute it  in mysql-1.
The same i will do with mysql-2 pods like will take a backup of mysql-1 and execute it in mysql-2. Now, my datas are all in pods,the data are in sync.

Now  created one more service as Cluster IP, with these im going to read the data of mysql-1 /mysql-2

```
![image](https://user-images.githubusercontent.com/54719289/118479712-44b17000-b709-11eb-8ee3-3034f952bd47.png)

```
I wont face any data consistency issue, like here there is no multiple writing option. Pods are in sync.
```


