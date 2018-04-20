# Script generated with Bloom
pkgdesc="ROS - The manipulation_msgs package"


pkgname='ros-kinetic-manipulation-msgs'
pkgver='0.2.1_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-actionlib-msgs'
'ros-kinetic-catkin'
'ros-kinetic-geometry-msgs'
'ros-kinetic-household-objects-database-msgs'
'ros-kinetic-message-generation'
'ros-kinetic-sensor-msgs'
'ros-kinetic-shape-msgs'
'ros-kinetic-std-msgs'
)

depends=('ros-kinetic-actionlib-msgs'
'ros-kinetic-geometry-msgs'
'ros-kinetic-household-objects-database-msgs'
'ros-kinetic-message-generation'
'ros-kinetic-message-runtime'
'ros-kinetic-sensor-msgs'
'ros-kinetic-shape-msgs'
'ros-kinetic-std-msgs'
)

conflicts=()
replaces=()

_dir=manipulation_msgs
source=()
md5sums=()

prepare() {
    cp -R $startdir/manipulation_msgs $srcdir/manipulation_msgs
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

