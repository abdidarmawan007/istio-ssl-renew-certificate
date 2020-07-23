# Renew ssl istio
- GKE 1.14.x
- Istio 1.3.x
- Sectigo ssl


## renew ssl
```
kubectl delete secret istio-ingressgateway-certs -n istio-system
```
```
kubectl create -n istio-system secret tls istio-ingressgateway-certs \
  --key folder-ssl/star_ssl.key \
  --cert folder-ssl/star_ssl.crt
```
```
kubectl rollout restart deployment istio-ingressgateway -n istio-system
```
```
istio-ingressgateway-54db5fd944-xmnl5     1/1     Terminating        0          24h
istio-ingressgateway-5dc5c5bc8d-mjgcr     1/1     Running            0          7s
```
