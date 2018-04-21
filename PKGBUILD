# Script generated with Bloom
pkgdesc="ROS - The agvs_gazebo package. Launch files and worlds to run Gazebo."
url='http://wiki.ros.org/agvs_gazebo'

pkgname='ros-kinetic-agvs-gazebo'
pkgver='0.1.3_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-agvs-description'
'ros-kinetic-agvs-pad'
'ros-kinetic-agvs-robot-control'
'ros-kinetic-catkin'
'ros-kinetic-effort-controllers'
'ros-kinetic-gazebo-ros'
'ros-kinetic-joint-state-controller'
'ros-kinetic-roscpp'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
'ros-kinetic-tf'
'ros-kinetic-velocity-controllers'
)

depends=('ros-kinetic-agvs-description'
'ros-kinetic-agvs-pad'
'ros-kinetic-agvs-robot-control'
'ros-kinetic-effort-controllers'
'ros-kinetic-gazebo-ros'
'ros-kinetic-joint-state-controller'
'ros-kinetic-roscpp'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
'ros-kinetic-tf'
'ros-kinetic-velocity-controllers'
)

conflicts=()
replaces=()

_dir=agvs_gazebo
source=()
md5sums=()

prepare() {
    cp -R $startdir/agvs_gazebo $srcdir/agvs_gazebo
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

