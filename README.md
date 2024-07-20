# CMakeLibTemplate
CMakeLibTemplate is a comprehensive template designed to streamline the process of building a library using CMake. This template provides a solid foundation, including a clear and organized directory structure, essential CMake configuration files, and best practices for library development. With CMakeLibTemplate, developers can quickly set up a new project with consistent build settings and focus on writing their library code, rather than spending time on initial configuration. Whether you are developing a static or shared library, this template ensures a smooth and efficient start to your CMake-based project.

# Build
    $ cmake -S <source_dir> -B <build_dir>
    $ cmake --build <build_dir>
# Install
    $ cmake --install <build_dir> --prefix <install_dir>