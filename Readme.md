# Docker Buildx Command to push an image into multi-architecture —

1. Open the Docker Desktop dashboard then open up Preferences (cog icon). Go to "Experimental Features" then turn it on and apply it.

2. Next create a new builder instance with "docker buildx create --use". This lets you specify multiple docker platforms at once.

3. To build your Dockerfile for typical x86 systems and Apple Silicon Macs, run "docker buildx build --platform linux/amd64,linux/arm64 --push -t <tag_to_push> ."

4. Once the build is finished, it will be automatically uploaded to your configured registry. Docker will also automatically manage the manifest list for you. This allows Docker to combine the separate builds for each architecture into a single "manifest". This means users can do a normal docker pull <image> and the Docker client will automatically work out the correct image for their CPU architecture