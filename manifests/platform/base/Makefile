operators/prometheus.yml:
	curl https://raw.githubusercontent.com/prometheus-operator/prometheus-operator/v0.53.1/bundle.yaml -o $@

operators/wordpress.yml:
	helm repo add bitpoke https://helm-charts.bitpoke.io
	helm template wordpress-operator bitpoke/wordpress-operator > $@

operators/wordpress-crd.yml:
	curl https://raw.githubusercontent.com/bitpoke/wordpress-operator/v0.12.1/config/crd/bases/wordpress.presslabs.org_wordpresses.yaml -o $@

observability/metrics-server.yml:
	curl -L https://github.com/kubernetes-sigs/metrics-server/releases/download/v0.5.2/components.yaml -o $@

operators/istio.yml:
	istioctl operator dump > $@

cert-manager/cert-manager.yml:
	helm repo add jetstack https://charts.jetstack.io
	helm template \
		cert-manager jetstack/cert-manager \
		--namespace platform \
		--version v1.7.1 \
		--set installCRDs=true \
		--set global.leaderElection.namespace=platform \
		> $@
