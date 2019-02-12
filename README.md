# CoreWindow sample

This is a small sample leveraging C++/WinRT and CMake to generate and build a Windows 10 UWP app that is not leveraging XAML.

   git clone https//github.com/coderox/CoreApp
   cd CoreApp
   cmake -DCMAKE_SYSTEM_NAME="WindowsStore" -DCMAKE_SYSTEM_VERSION="10.0" .
   cmake --build .