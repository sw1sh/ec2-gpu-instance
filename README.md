# ec2-gpu-instance
Ansible provision scripts for configuration of an Amazon EC2 GPU instance.

## Amazon instance and AMI

These provision scripts should be applied to an EC2 GPU instance configured with an *Ubuntu Server 14.04 LTS (HVM), SSD Volume Type - ami-47a23a30* machine image.

## Installed software

The following software is installed on the instance:
- **common**; regular packages like java8, git, curl, make, etc.
- **cuda**; Nvidia drivers, CUDA, CUDNN
- **tools**; Anaconda (python 2), Theano, Caffe, Keras

## Running the ansible-playbook

To allow the installation of the NVIDIA® cuDNN – GPU Accelerated Deep Learning libraries, please download the binaries from https://developer.nvidia.com/cudnn.

Perform the following steps to successfully install the instance using the ansible playbook:

1. Make sure ansible is installed (preferably in python 2 environment, if not install using `pip install ansible`).
2. Add the cudnn-7.5-linux-x64-v5.0-ga.tgz file to the **roles/gpu/files/**-folder.
3. Add the public ip or dns of the instance to the hosts file.
4. Add the path of the pem key file to the ansible.cfg file.
5. Run the playbook from the root of this repository by executing: `ansible-playbook gpu-instance.yml`.
