# ========================
# React App Commands
# ========================
npx create-react-app myapp         # Create a new React app  
cd myapp                           # Move into the project folder  
npm start                          # Run React development server  
npm run build                      # Create production build of React app  

# ========================
# Docker Commands
# ========================
docker build -t myapp:1 .          # Build Docker image with tag "1"  
docker tag myapp:1 myrepo/myapp:1  # Tag local image for Docker Hub  
docker push myrepo/myapp:1         # Push image to Docker Hub  
docker pull myrepo/myapp:1         # Pull image from Docker Hub  
docker run -p 3000:3000 myapp:1    # Run image and expose port 3000  

# ========================
# Kubernetes Basic Commands
# ========================
kubectl create deployment myapp --image=myrepo/myapp:1  # Create deployment  
kubectl get deployments                                # List deployments  
kubectl get pods                                       # List pods  
kubectl get services                                   # List services  
kubectl expose deployment myapp --type=NodePort --port=3000  # Expose app to outside  
kubectl delete deployment myapp                        # Delete deployment  

# ========================
# Kubernetes Rollout Commands
# ========================
kubectl set image deployment/myapp myapp=myrepo/myapp:2  # Update deployment to new version  
kubectl rollout status deployment/myapp                 # Check rollout status  
kubectl rollout history deployment/myapp                # Show rollout history
kubectl rollout undo deployment/myapp                   # Rollback to previous version
kubectl rollout undo deployment/myapp --to-revision=2   # Rollback to specific revision
kubectl rollout restart deployment/myapp                # Restart pods in deployment
