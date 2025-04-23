# Node.js Docker Application

This project is a simple Node.js application packaged with Docker and deployed on OpenShift. Below are the details for setting up and running the application.

## Project Structure

```
nodejs-docker-app
├── src
│   └── app.js                # Main application logic
├── Dockerfile                 # Docker image build instructions
├── .dockerignore              # Files to ignore when building the Docker image
├── manifests
│   ├── deployment.yaml        # Kubernetes deployment configuration
│   ├── service.yaml           # Kubernetes service configuration
│   └── route.yaml             # OpenShift route configuration
├── pipeline
│   ├── pipeline.yaml          # OpenShift pipeline configuration
│   ├── tasks
│   │   ├── git-clone.yaml     # Task for cloning the Git repository
│   │   ├── build.yaml         # Task for building the Docker image
│   │   └── apply-manifests.yaml # Task for applying Kubernetes manifests
├── package.json               # npm configuration file
└── package-lock.json          # Dependency version lock file
```

## Setup Instructions

1. **Clone the Repository**
   Clone the repository to your local machine using:
   ```
   git clone <repository-url>
   ```

2. **Navigate to the Project Directory**
   ```
   cd nodejs-docker-app
   ```

3. **Install Dependencies**
   Install the required dependencies using npm:
   ```
   npm install
   ```

4. **Build the Docker Image**
   Build the Docker image using the provided Dockerfile:
   ```
   docker build -t <your-image-name> .
   ```

5. **Push to Quay.io**
   After building the image, push it to Quay.io:
   ```
   docker push <your-quay-io-repo>/<your-image-name>
   ```

6. **Deploy to OpenShift**
   Use the OpenShift pipeline to deploy the application. Ensure you have the necessary permissions and access to the OpenShift cluster.

## Usage

After deployment, you can access the application via the OpenShift route defined in `manifests/route.yaml`. The application will respond to requests as defined in `src/app.js`.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.