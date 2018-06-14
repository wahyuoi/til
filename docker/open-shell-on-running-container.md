Open Shell on Running Container
---

use `docker ps` to show container's name. To open new terminal with new instance of container's shell, just need to run:

```
docker exec -i -t CONTAINER_NAME /bin/bash

```
