# aws-ros-monitoringmessages-ros2
**Note: This repository is under active development. The package provided here is a release candidate; the API may change without notice and no support is provided for it at the moment.**
`ros_monitoring_msgs` package for facilitating the use of monitoring-related AWS cloud services.

This package primarily provides ROS message types for use with Amazon CloudWatch, and is used by the [cloudwatch_metrics_collector](https://github.com/aws-robotics/cloudwatchmetrics-ros2) node. 
For example, the `MetricData` message corresponds to a [MetricDatum](https://docs.aws.amazon.com/AmazonCloudWatch/latest/APIReference/API_MetricDatum.html), and the `MetricDimension` to [Dimension](https://docs.aws.amazon.com/AmazonCloudWatch/latest/APIReference/API_Dimension.html). 

### Supported ROS Distributions
* Dashing 

### Build status
GitHub Action Status
* master: ![Build & Test](https://github.com/aws-robotics/monitoringmessages-ros2/workflows/Build%20&%20Test/badge.svg?branch=master&event=schedule)
* release-latest: ![Build & Test release-latest](https://github.com/aws-robotics/monitoringmessages-ros2//workflows/Build%20&%20Test%20release-latest/badge.svg?event=schedule)

* Travis CI:
    * "master" branch [![Build Status](https://travis-ci.org/aws-robotics/monitoringmessages-ros2.svg?branch=master)](https://travis-ci.org/aws-robotics/monitoringmessages-ros2/branches)
* ROS build farm:
    * ROS Dashing @ u18.04 Bionic **Not Yet Released**

## Installation

### Binaries
**Binaries not yet available in apt**
On Ubuntu you can install the latest version of this package using the following command

        sudo apt-get update
        sudo apt-get install -y ros-$ROS_DISTRO-ros-monitoring-msgs

### Building from Source

To build from source you'll need to create a new workspace, clone and checkout the latest release branch of this repository, install all the dependencies, and compile. If you need the latest development features you can clone from the `master` branch instead of the latest release branch. While we guarantee the release branches are stable, __the `master` should be considered to have an unstable build__ due to ongoing development. 

- Create a ROS workspace and a source directory

        mkdir -p ~/ros-workspace/src

- Clone the package into the source directory . 

        cd ~/ros-workspace/src
        git clone https://github.com/aws-robotics/monitoringmessages-ros2.git

- Install dependencies

        cd ~/ros-workspace 
        sudo apt-get update && rosdep update
        rosdep install --from-paths src --ignore-src -r -y
        
_Note: If building the master branch instead of a release branch you may need to also checkout and build the master branches of the packages this package depends on._

- Build the packages

        cd ~/ros-workspace && colcon build

- Configure ROS library path

        source ~/ros-workspace/install/local_setup.bash

