# Preetha – ECS & EKS CodePipeline Starter

## Quick start
1. Create two ECR repos: `ecs-hello` and `eks-hello` (or change names in buildspecs).
2. Push this repo to GitHub/CodeCommit.
3. Create **Pipeline A (ECS)**:
   - CodeBuild: use `buildspec-ecs.yml`, set env `IMAGE_REPO_NAME=ecs-hello`, `CONTAINER_NAME=app`.
   - Deploy stage: ECS deploy action → your cluster/service; image defs file `imagedefinitions.json`.
4. Create **Pipeline B (EKS)**:
   - CodeBuild: use `buildspec-eks.yml`, set env `IMAGE_REPO_NAME=eks-hello`, `EKS_CLUSTER_NAME=<your-cluster>`.
   - Add the CodeBuild role into EKS aws-auth as `system:masters` (lab only).

App runs on `:8080` and returns a hello message.
