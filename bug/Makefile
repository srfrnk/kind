bug:
	make -C .. build
	- ../bin/kind delete cluster
	../bin/kind create cluster

	docker build -t bug:1 .
	docker build -t bug:2 .

	../bin/kind load docker-image bug:1
	../bin/kind load docker-image bug:2

	sleep 10

	kubectl run --image bug:1 bug-1
	kubectl run --image bug:2 bug-2

	sleep 10

	kubectl describe pod bug-1
	kubectl describe pod bug-2
