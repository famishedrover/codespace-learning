# Use the RHEL 7 base image
FROM registry.access.redhat.com/rhel7:latest

# Enable RHEL 7 repositories
RUN subscription-manager repos --enable rhel-7-server-rpms

# Install required packages: CMake, Ninja, Python 3.9, and pip
RUN yum install -y cmake3 ninja-build python39 python39-pip

# Create symbolic links to simplify the use of CMake and Python
RUN ln -s /usr/bin/cmake3 /usr/bin/cmake && \
    ln -s /usr/bin/python3.9 /usr/bin/python && \
    ln -s /usr/bin/pip-3.9 /usr/bin/pip

# Clean up the Yum cache to reduce the image size
RUN yum clean all

# Set the default command to run when the container starts
CMD ["/bin/bash"]