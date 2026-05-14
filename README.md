# openclaw-gke-test

## Prerequisites
1. An existing GKE cluster configured with `kubectl` access.
2. A Gemini API key (can be obtained from [Google AI Studio](https://aistudio.google.com/)).

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