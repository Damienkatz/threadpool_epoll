# threadpool_epoll
MySQL threadpool and epoll connection handler. Allows 100x simultaneous clients vs thread-per-connection.

# Usage

First, compile the plugin and install in to plugin dir

    cp -r . /path/to/mysql-src/plugin/threadpool_epoll
    cd /path/to/mysql-src
    cmake . -DBUILD_CONFIG=mysql_release -DFORCE_INSOURCE_BUILD=1
    cd plugin/threadpool_epoll
    make
    make install

Then, load the plugin into mysql

    mysql> INSTALL PLUGIN THREADPOOL_EPOLL SONAME 'libthreadpool_epoll.so';
