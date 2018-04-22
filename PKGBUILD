# Script generated with Bloom
pkgdesc="ROS - rqt_multiplot provides a GUI plugin for visualizing numeric values in multiple 2D plots using the Qwt plotting backend."


pkgname='ros-kinetic-rqt-multiplot'
pkgver='0.0.7_3'
pkgrel=1
arch=('any')
license=('GNU Lesser General Public License (LGPL)'
)

makedepends=('qwt'
'ros-kinetic-catkin'
'ros-kinetic-rosbag'
'ros-kinetic-roscpp'
'ros-kinetic-rqt-gui'
'ros-kinetic-rqt-gui-cpp'
'ros-kinetic-variant-topic-tools'
)

depends=('ros-kinetic-rosbag'
'ros-kinetic-roscpp'
'ros-kinetic-rqt-gui'
'ros-kinetic-rqt-gui-cpp'
'ros-kinetic-variant-topic-tools'
)

conflicts=()
replaces=()

_dir=rqt_multiplot
source=()
md5sums=()

prepare() {
    cp -R $startdir/rqt_multiplot $srcdir/rqt_multiplot
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

