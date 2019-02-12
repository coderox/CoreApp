# CoreWindow sample

This is a small sample leveraging C++/WinRT and CMake to generate and build a Windows 10 UWP app that is not leveraging XAML.

Make sure you have [CMake](https://cmake.org/) installed.
   `git clone https//github.com/coderox/CoreApp`
   
Change into cloned directory and generate with the following:
   `cmake -DCMAKE_SYSTEM_NAME="WindowsStore" -DCMAKE_SYSTEM_VERSION="10.0" .`

To build, either open generated solution in Visual Studio, or use following command
   `cmake --build .`