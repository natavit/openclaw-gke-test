# openclaw-gke-test

## Deploy
```bash
export GEMINI_API_KEY="..."
./deploy.sh

kubectl get secret openclaw-secrets -n openclaw -o jsonpath='{.data.OPENCLAW_GATEWAY_TOKEN}' | base64 -d

kubectl port-forward svc/openclaw 18789:18789 -n openclaw

open http://localhost:18789
```

## Re-deploy
```bash
./deploy.sh
```

## Delete
```bash
./deploy.sh --delete
```