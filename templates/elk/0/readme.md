## Prerequisites<a name="prerequisites"></a>

To run a container using this image, you will need the following:

- **Docker**

	Install [Docker](https://docker.com/), either using a native package (Linux) or wrapped in a virtual machine (Windows, OS X – e.g. using [Boot2Docker](http://boot2docker.io/) or [Vagrant](https://www.vagrantup.com/)).

	**Note** – As the *sebp/elk* image is based on a Linux image, users of Docker for Windows will need to ensure that [Docker is using Linux containers](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).
	 

- **A minimum of 4GB RAM assigned to Docker**

	Elasticsearch alone needs at least 2GB of RAM to run.

	With Docker for Mac, the amount of RAM dedicated to Docker can be set using the UI: see [How to increase docker-machine memory Mac](http://stackoverflow.com/questions/32834082/how-to-increase-docker-machine-memory-mac/39720010#39720010) (Stack Overflow).

- **A limit on mmap counts equal to 262,144 or more**

	**<span style="color:red">!! This is the most frequent reason for Elasticsearch failing to start since Elasticsearch version 5 was released.</span>**

	On Linux, use `sysctl vm.max_map_count` on the host to view the current value, and see [Elasticsearch's documentation on virtual memory](https://www.elastic.co/guide/en/elasticsearch/reference/5.0/vm-max-map-count.html#vm-max-map-count) for guidance on how to change this value. Note that the limits **must be changed on the host**; they cannot be changed from within a container.

	If using Docker for Mac, then you will need to start the container with the `MAX_MAP_COUNT` environment variable (see [Overriding start-up variables](#overriding-variables)) set to at least 262144 (using e.g. `docker`'s `-e` option) to make Elasticsearch set the limits on mmap counts at start-up time.