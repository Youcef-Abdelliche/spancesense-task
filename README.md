# spacesense-task
## Setup project

### Pre-requisites

Make sure you have the following pre-installed components:

- [Docker](https://docs.docker.com/get-docker/)
- Postman installed (Download: [Postman](https://www.postman.com/downloads/))

### Step 1 : Build Docker Image
```bash
docker build -t segmentationimage .
```

### Step 2 : Run Docker Container
```bash
docker run --names mycontainer -d segmentationimage
```

### Step 3 : Get Container IP Address
```bash
container_ip=$(docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' mycontainer)
```

```bash
echo "Container IP Address: $container_ip"
```

### Step 4 : Send POST Request Using Postman
(You can use any other tool to test endpoint)
1. Open Postman.

2. Create a new request.

3. Set the request type to POST.

4. Enter the following URL (Replace $container_ip with the actual IP address obtained in Step 3):
```
https://$container_ip/segment-image/
```

5. In the request body section, select the "form-data" option.

6. Add a key-value pair:

    - Key: file
    - Value: Select the file option to upload your image file. You can use images in resources folder.

7. Select the "Send" button to initiate the request. Please be patient, as the processing time may vary based on your CPU performance.
