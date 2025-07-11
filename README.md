<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  
</head>
<body>

  <h1>🐳 MySQL StatefulSet on Kubernetes</h1>

  <p>
    This project demonstrates how to deploy MySQL using a Kubernetes <strong>StatefulSet</strong> with persistent volumes, secrets, and config maps. It ensures that each pod retains its identity and storage across restarts.
  </p>

  <h2>🚀 Features</h2>
  <ul>
    <li>StatefulSet with <code>volumeClaimTemplates</code></li>
    <li>Secure secrets using Kubernetes <code>Secret</code> object</li>
    <li>Custom configuration via <code>ConfigMap</code></li>
    <li>Stable network identity with a headless <code>Service</code></li>
    <li>Namespace-based deployment (e.g., <code>mysql</code>)</li>
  </ul>

  <h2>📁 File Structure</h2>
  <pre>
.
├── secret.yaml
├── configmap.yaml
├── service.yaml
└── statefulset.yaml
  </pre>

  <h2>🔧 Usage</h2>
  <ol>
    <li>Create the namespace: <code>kubectl create namespace mysql</code></li>
    <li>Apply the secret: <code>kubectl apply -f secret.yaml -n mysql</code></li>
    <li>Apply the configmap: <code>kubectl apply -f configmap.yaml -n mysql</code></li>
    <li>Apply the service: <code>kubectl apply -f service.yaml -n mysql</code></li>
    <li>Deploy the StatefulSet: <code>kubectl apply -f statefulset.yaml -n mysql</code></li>
  </ol>

  <h2>✅ Verification</h2>
  <ul>
    <li>Check pods: <code>kubectl get pods -n mysql</code></li>
    <li>Check PVCs: <code>kubectl get pvc -n mysql</code></li>
    <li>Check logs: <code>kubectl logs mysql-stateful-0 -n mysql</code></li>
  </ul>

  <h2>📌 Notes</h2>
  <ul>
    <li>Base64 encode sensitive data before storing in <code>Secret</code></li>
    <li>This setup is ideal for local clusters like <code>kind</code> or <code>minikube</code></li>
    <li>Adjust <code>StorageClass</code> and <code>resources</code> as per your environment</li>
  </ul>

  <p>Built with ❤️ by Uday Kiran</p>

</body>
</html>
