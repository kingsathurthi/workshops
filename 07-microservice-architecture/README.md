# Lab 7: Creating a microservice architecture

In this lab we are going to deploy multiple services from different teams and expose them using a shared domain, but each on their own path. We will use on-the-fly Knative services for speed and simplicity.

## Prerequisites

1. You are familiar with Knative. Did you try following the [Knative workshop](../04-knative/README.md)?
2. Knative is enabled in Otomi. (Check the `Apps` section under `Platform`.)
3. Two teams are created. We will refer to them as `team-a` and `team-b`. (It is not necessary to `Deploy` first.)

## Instructions

1. Select team `team-a` in the top bar, select `Services` from the `Team team-a` menu section and click on `Create Service`, and choose `New knative service`.

2. Provide the following values and `submit`:

- name: `sir`
- Run As User: `1001`
- Repository: `otomi/nodejs-helloworld`
- Tag: `v1.2.12`
- Limits: `CPU=100m`, `Memory=128Mi`
- Requests: `CPU=50m`, `Memory=64Mi`
- env: `TARGET=world, I just woke up!`, `SERVANTS=servant-1,servant-2`
- Exposure: `Ingress`
- Uncheck `Use team domain`
- Check `Scale to zero`
- host: `hello-multi` (DNS zone can be left as-is)

Click `Deploy` to start the service and domain registration, as that might take time. Plus we want the service to go to sleep as we intend to wake it up later (it serves a purpose, hope you spot it later on ;).

3. Under the same team create the last `New knative service` service with the same values but the following diff and `submit`:

- name: `informant`
- Exposure: `Cluster`
- Leave `Scale to zero` unchecked

4. Under the same team create another `New knative service` service  with the same values but with the following diff and `submit`:

- name: `servant-1`
- paths: `/servant-1`
- env: `TARGET=sir`
 
5. Select team `team-b` and create a `New knative service` service with the same values but the following diff and `submit`:

- name: `servant-2`
- paths: `/servant-2`
- env: `TARGET=sir`, `INFORMANT=informant.team-a` 

6. Now click `Deploy Changes` again and watch the deployment finish in Drone.

## Conclusion

In effect what we have done is create the following workloads for `team-a`:

- `master.team-a` exposed via `https://hello-multi.$domain`
- `servant-1.team-a` exposed via `https://hello-multi.$domain/servant-1`
- `informant.team-a` not exposed publicly, but only able to receive requests from `servant-2.team-b`.

And for `team-b`:

- `servant-2.team-b` exposed via `https://hello-multi.$domain/servant-2`

Bonus: Add network policies to make sure no unforeseen traffic is routed :)

Go to the [next lab](../08-argocd/README.md)
