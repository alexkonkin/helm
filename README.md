cd /path/to/webapp-color
git init
git remote add origin https://github.com/alexkonkin/helm.git
helm package .
helm repo index . --url https://alexkonkin.github.io/helm/
git checkout -b gh-pages
git add webpage-server-02-0.1.1.tgz index.yaml
git commit -m "Add webapp-color Helm chart"
git push -u origin gh-pages
# Go to GitHub Settings → Pages and set branch to gh-pages
helm repo add alexkonkin https://alexkonkin.github.io/helm/
helm repo update
helm install my-webapp alexkonkin/webapp-color
