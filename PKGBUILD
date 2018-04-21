# Script generated with Bloom
pkgdesc="ROS - The agvs_robot_control package. Robot controller that interacts with Gazebo motor controllers."
url='http://wiki.ros.org/agvs_robot_control'

pkgname='ros-kinetic-agvs-robot-control'
pkgver='0.1.3_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-ackermann-msgs'
'ros-kinetic-catkin'
'ros-kinetic-diagnostic-msgs'
'ros-kinetic-diagnostic-updater'
'ros-kinetic-geometry-msgs'
'ros-kinetic-message-generation'
'ros-kinetic-nav-msgs'
'ros-kinetic-robotnik-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
'ros-kinetic-tf'
)

depends=('ros-kinetic-ackermann-msgs'
'ros-kinetic-diagnostic-msgs'
'ros-kinetic-diagnostic-updater'
'ros-kinetic-geometry-msgs'
'ros-kinetic-message-runtime'
'ros-kinetic-nav-msgs'
'ros-kinetic-robotnik-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
'ros-kinetic-tf'
)

conflicts=()
replaces=()

_dir=agvs_robot_control
source=()
md5sums=()

prepare() {
    cp -R $startdir/agvs_robot_control $srcdir/agvs_robot_control
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

