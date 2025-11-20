Manifiestos Kubernetes para frontend y backend

Archivos creados / combinados:
- namespaces/frontend-ns.yaml  -> Namespace para frontend
- namespaces/backend-ns.yaml   -> Namespace para backend
-- backend/backend.yaml        -> Deployment + Service del backend (image: tomascv/backend-licomart:latest, puerto 8000)
-- frontend/frontend.yaml      -> Deployment + Service del frontend (image: tomascv/frontend-licomart:latest, puerto 80)

Instrucciones rápidas:

1) Aplicar todos los manifiestos (ahora cada carpeta tiene un único YAML por componente):

   kubectl apply -f k8s/namespaces/frontend-ns.yaml
   kubectl apply -f k8s/namespaces/backend-ns.yaml
   kubectl apply -f k8s/backend/backend.yaml
   kubectl apply -f k8s/frontend/frontend.yaml

2) Escalar réplicas (ejemplo):

   kubectl scale deployment/frontend-deployment --replicas=5 -n frontend-ns
   kubectl scale deployment/backend-deployment --replicas=4 -n backend-ns
