# An overly engineered website
An overly engineered website that uses Django with K8s deployed on DigitalOcean (WIP), for fun

<img src="https://github.com/benji011/An-overly-engineered-website/blob/main/app/static/img/infra.png" alt="My tiny infrastructure">


# Usage

### 1. Create your own secrets in .env file

```bash
DEBUG=<your_value_here>
SECRET_KEY=<your_secret_key_here>
ALLOWED_HOSTS=<your_allowed_hosts_value_here>
```

### 2. Generate secrets.yml from .env file

```bash
kubectl create secret generic prod-secrets --from-env-file=.env
```

### 3. Apply development.yml

```bash
kubectl apply -f kubernetes/deployments/deployment.yml
```

### 4. Apply service.yml

```bash
kubectl apply -f kubernetes/services/service.yml
```

Open app on [http://localhost](http://localhost)
