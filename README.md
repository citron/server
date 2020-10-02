<!--
# Copyright (c) 2018-2020, NVIDIA CORPORATION. All rights reserved.
#
# Redistribution and use in source and binary forms, with or without
# modification, are permitted provided that the following conditions
# are met:
#  * Redistributions of source code must retain the above copyright
#    notice, this list of conditions and the following disclaimer.
#  * Redistributions in binary form must reproduce the above copyright
#    notice, this list of conditions and the following disclaimer in the
#    documentation and/or other materials provided with the distribution.
#  * Neither the name of NVIDIA CORPORATION nor the names of its
#    contributors may be used to endorse or promote products derived
#    from this software without specific prior written permission.
#
# THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS ``AS IS'' AND ANY
# EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
# IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR
# PURPOSE ARE DISCLAIMED.  IN NO EVENT SHALL THE COPYRIGHT OWNER OR
# CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL,
# EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
# PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR
# PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY
# OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
# (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
# OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
-->

[![License](https://img.shields.io/badge/License-BSD3-lightgrey.svg)](https://opensource.org/licenses/BSD-3-Clause)

# Triton Inference Server

**LATEST RELEASE: You are currently on the master branch which tracks
under-development progress towards the next release. The latest
release of the Triton Inference Server is 2.2.0 and is available on
branch
[r20.08](https://github.com/triton-inference-server/server/tree/r20.08).**

Triton Inference Server provides a cloud and edge inferencing solution
optimized for both CPUs and GPUs. Triton supports an HTTP/REST and
GRPC protocol that allows remote clients to request inferencing for
any model being managed by the server. For edge deployments, Triton is
available as a shared library with a C API that allows the full
functionality of Triton to be included directly in an
application.

The current release of the Triton Inference Server is 2.2.0 and
corresponds to the 20.08 release of the tensorrtserver container on
[NVIDIA GPU Cloud (NGC)](https://ngc.nvidia.com). The branch for this
release is
[r20.08](https://github.com/triton-inference-server/server/tree/r20.08).

## Features

* [Multiple framework support](docs/model_repository.md). Triton can
  manage any number and mix of models (limited by system disk and
  memory resources). Triton supports TensorRT, TensorFlow GraphDef,
  TensorFlow SavedModel, ONNX, PyTorch, and Caffe2 NetDef model
  formats. Both TensorFlow 1.x and TensorFlow 2.x are
  supported. Triton also supports TensorFlow-TensorRT and
  ONNX-TensorRT integrated models.

## Documentation

[Triton architecture](docs/architecture.md) gives a high-level
overview of the structure and capabilities of the inference server.
Additional documentation is divided into *user* and *developer*
sections. The *user* documentation describes how to use Triton as an
inference solution, including information on how to configure Triton,
how to organize and configure your models, how to use the C++ and
Python clients, etc. The *developer* documentation describes how to
build and test Triton and also how Triton can be extended with new
functionality.

The Triton [Release
Notes](https://docs.nvidia.com/deeplearning/triton-inference-server/release-notes/index.html)
and [Support
Matrix](https://docs.nvidia.com/deeplearning/dgx/support-matrix/index.html)
indicate the required versions of the NVIDIA Driver and CUDA, and also
describe supported GPUs.

### User Documentation

The [quickstart](docs/quickstart.md) walks you through all the steps
required to install and run Triton with an example image
classification model and then use an example client application to
perform inferencing using that model. The quickstart demonstrates how
[Triton supports both GPU systems and CPU-only
systems](docs/quickstart.md#run-triton).

getting your models into triton. how to set up model repository. how
to work with model configuration.  handling custom operations. models
and schedulers

client libraries and examples

understand triton performance, optimizing your models on triton, model analyzer

The [version 1 to version 2 migration
information](docs/v1_to_v2.md) is helpful if you are moving to
version 2 of Triton from previously using version 1.

NVIDIA publishes a number of [deep learning
examples](https://github.com/NVIDIA/DeepLearningExamples) that use
Triton.

If you are using Kubernetes a simple example of how to [deploy Triton
using Kubernetes and Helm](deploy/single_server/README.rst) may be
helpful.

### Developer Documentation

build server

test

inference protocols for own clients

C API for inprocess

backend API

## Papers and Presentation

* [Maximizing Deep Learning Inference Performance with NVIDIA Model
  Analyzer](https://developer.nvidia.com/blog/maximizing-deep-learning-inference-performance-with-nvidia-model-analyzer/).

* [High-Performance Inferencing at Scale Using the TensorRT Inference
  Server](https://developer.nvidia.com/gtc/2020/video/s22418).

* [Accelerate and Autoscale Deep Learning Inference on GPUs with
  KFServing](https://developer.nvidia.com/gtc/2020/video/s22459).

* [Deep into Triton Inference Server: BERT Practical Deployment on
  NVIDIA GPU](https://developer.nvidia.com/gtc/2020/video/s21736).

* [Maximizing Utilization for Data Center Inference with TensorRT
  Inference Server](https://on-demand-gtc.gputechconf.com/gtcnew/sessionview.php?sessionName=s9438-maximizing+utilization+for+data+center+inference+with+tensorrt+inference+server).

* [NVIDIA TensorRT Inference Server Boosts Deep Learning
  Inference](https://devblogs.nvidia.com/nvidia-serves-deep-learning-inference/).

* [GPU-Accelerated Inference for Kubernetes with the NVIDIA TensorRT
  Inference Server and
  Kubeflow](https://www.kubeflow.org/blog/nvidia_tensorrt/).

## Contributing

Contributions to Triton Inference Server are more than welcome. To
contribute make a pull request and follow the guidelines outlined in
[CONTRIBUTING.md](CONTRIBUTING.md).

## Reporting problems, asking questions

We appreciate any feedback, questions or bug reporting regarding this
project. When help with code is needed, follow the process outlined in
the Stack Overflow (https://stackoverflow.com/help/mcve)
document. Ensure posted examples are:

* minimal – use as little code as possible that still produces the
  same problem

* complete – provide all parts needed to reproduce the problem. Check
  if you can strip external dependency and still show the problem. The
  less time we spend on reproducing problems the more time we have to
  fix it

* verifiable – test the code you're about to provide to make sure it
  reproduces the problem. Remove all other problems that are not
  related to your request/question.
