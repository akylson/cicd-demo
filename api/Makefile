repo = api
version = 1.0
account=$(shell aws sts get-caller-identity --query "Account" --output text)

build:
	docker build -t $(repo):$(version) . 
login: 
	aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin $(account).dkr.ecr.us-east-1.amazonaws.com
push: login
	docker tag $(repo):$(version) $(account).dkr.ecr.us-east-1.amazonaws.com/$(repo):$(version)
	docker push $(account).dkr.ecr.us-east-1.amazonaws.com/$(repo):$(version)
deploy:
	cat kubernetes/deploy.yaml | sed "s/IMAGEVERSION/$(version)/g;s/ACCOUNT/$(account)/g" | kubectl apply -f -