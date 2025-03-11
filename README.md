# Trading Application (Deribit_Trading)

This project is a trading application that connects to a cryptocurrency exchange via WebSockets and allows the user to place, 
cancel, modify orders, fetch order books, and view current positions. The application has been optimized for performance, including 
asynchronous network communication, memory management improvements, and threading optimizations.



## Prerequisites

### System Requirements

- **C++ Compiler**: A compiler with C++17 support, such as:
  - GCC 7+ (Linux)
  - Clang 7+ (Linux/macOS)
  - MSVC 2017+ (Windows)
- **CMake**: Version 3.x or higher.
- **Boost Libraries**: Required for utilities like `boost::asio` for network communication.
- **OpenSSL**: For secure WebSocket and API communication.
- **Git**: For version control and cloning the repository.

### Dependencies

- `nlohmann/json` (for JSON parsing and handling)
- WebSocket library
- Boost Libraries (including `boost::asio`)

## Installation

### 1. Clone the repository:

```bash
git clone https://github.com/u0m5e0s9h/WebSocket_HFT.git
cd Websocket_HFT
```
### 2. Install dependencies:
-Install Boost Library
 Boost is required for this project. If Boost is not already installed, follow these steps:

1. Install Boost using your package manager:

Ubuntu/Debian:
```bash
sudo apt-get install libboost-all-dev
```
macOS (with Homebrew):
```bash
brew install boost
```
Windows: Download and install Boost from the Boost website.
[Link here](https://www.boost.org/)

2. Install OpenSSL
Ubuntu/Debian:
```bash
sudo apt-get install libssl-dev
```
macOS (with Homebrew):
```bash
brew install openssl
```
Windows: Download and install OpenSSL from the OpenSSL website.
[Link here](https://www.openssl.org/)

3. Install Other Dependencies
You may use a package manager like vcpkg to install libraries:
```bash
./vcpkg install nlohmann-json websocketp
```

4. Build & Setup the project with CMake:
a) Create a build directory:
```bash
mkdir build
cd build
```
b) Run CMake to configure the project:
```bash
cmake .. -G "MinGW Makefiles"
```
Note: on windows, replace "MinGW Makefiles" with "Visual Studio 17 2022"if using MSVC

c) Compile the project:
```bash
cmake --build . --config Release
```
This will generate the executable file deribit_trader.exe

4. Run the application:
```bash
./build/Release/deribit_trader.exe     # windows
./build/deribit_trader                 #Linux/maxOS
```

## Usage
Once the application is running, you will be prompted with a menu for selecting trading operations:

mathematica
```bash
--- Trading Menu ---
1. Place Order
2. Cancel Order
3. Modify Order
4. Get Order Book
5. View Current Positions
6. Exit
```

## order Placement &Management
Example Workflow
1. Place Order:

Select option 1 and input the instrument name (e.g., BTC-PERPETUAL), amount, and price.
The application will asynchronously place a buy order and show the response.

2. Cancel Order:

Select option 2 and input the order ID to cancel the order.
The application will asynchronously cancel the order and show the response.

3. Modify Order:

Select option 3 and input the order ID, new amount, and new price to modify the existing order.

4. Get Order Book:

Select option 4 and input the instrument name to view the order book.

5. View Current Positions:

Select option 5 to view the current positions in your account.

6. Exit:

Select option 6 to exit the application.

## Optimizations
- Memory Management:
Uses std::make_unique for efficient memory management, preventing memory leaks and reducing overhead.

- Asynchronous Network Communication:
Network requests (placing, canceling, and modifying orders) are handled asynchronously to avoid blocking the main thread, improving responsiveness.

-Thread Management:
The use of std::async allows for concurrent execution of I/O operations, enhancing user experience by not blocking the main application thread.

-SIMD/Parallelization:
Future improvements can include SIMD (Single Instruction, Multiple Data) optimizations for parallelizing large-scale data processing tasks, such as order book analysis.
















