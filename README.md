# LanScan - Network Scanner and Diagnostic Tool

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![C++](https://img.shields.io/badge/C++-17-blue.svg)](https://isocpp.org/)
[![Qt](https://img.shields.io/badge/Qt-6.9.1-brightgreen.svg)](https://www.qt.io/)
[![CMake](https://img.shields.io/badge/CMake-3.16+-064F8C.svg)](https://cmake.org/)
[![Build](https://img.shields.io/badge/build-passing-brightgreen.svg)](https://github.com/paolosereno/LanScan)
[![Tests](https://img.shields.io/badge/tests-15%2F19%20passing-yellow.svg)](https://github.com/paolosereno/LanScan)

Network scanner application with advanced diagnostics and metrics visualization.

## Features

### ✅ Implemented (Phase 0-5)

**Network Discovery & Scanning** (Phase 0-1)
- ✅ Network device discovery (IP, hostname, MAC)
- ✅ Multi-threaded IP range scanning
- ✅ Ping-based host discovery (cross-platform Windows/Linux/macOS)
- ✅ DNS reverse lookup
- ✅ ARP table parsing
- ✅ MAC vendor identification (40+ manufacturers)
- ✅ Service detection (40+ common ports)
- ✅ Two scan strategies (Quick & Deep)

**Metrics & Diagnostics** (Phase 2)
- ✅ Real-time latency monitoring (min/max/avg/median/stdDev)
- ✅ Jitter calculation (standard deviation & consecutive)
- ✅ Packet loss detection with burst pattern analysis
- ✅ Connection quality scoring (0-100 weighted algorithm)
- ✅ Continuous ping monitoring with history tracking
- ✅ Port scanning (TCP Quick/Full/Custom modes)
- ✅ Metrics aggregation with dependency injection

**Persistence & Data Management** (Phase 3)
- ✅ SQLite database with full schema (devices, ports, metrics)
- ✅ Repository pattern with CRUD operations
- ✅ In-memory LRU cache for performance
- ✅ CSV export functionality
- ✅ JSON export functionality
- ✅ Cross-platform settings management (QSettings)
- ✅ Configuration validation

**Application Layer & Controllers** (Phase 4)
- ✅ Multi-threaded scan coordination (ScanCoordinator with QThreadPool)
- ✅ Thread-safe progress tracking (ProgressTracker with std::atomic)
- ✅ Scan workflow controller (quick/deep/custom scan modes)
- ✅ Metrics collection controller (continuous monitoring)
- ✅ Export operations controller (CSV/JSON/XML/HTML)
- ✅ Scan profile management with JSON persistence
- ✅ Favorite devices management with tagging support

**UI Foundation & Views** (Phase 5)
- ✅ MVVM architecture pattern implementation
- ✅ Qt Designer UI layouts (mainwindow, device table, scan dialog)
- ✅ Main window with menu bar, toolbar, status bar
- ✅ Device table widget with sorting and filtering
- ✅ Custom delegates (LED status indicator, quality score progress bar)
- ✅ Scan configuration dialog with input validation
- ✅ Context menu with device actions
- ✅ Full dependency injection architecture
- ✅ Signal/slot connections for async UI updates

### 🚧 Planned (Phase 6+)
- Charts and metrics visualization (QtCharts integration)
- Advanced diagnostics (traceroute, MTU discovery, bandwidth test)
- UI polish with dark/light themes
- Historical data tracking with trend analysis
- Network topology visualization
- Wake-on-LAN support

## Technology Stack

- **Framework**: Qt 6.x (Widgets, Network, Charts)
- **Language**: C++ 17
- **Build System**: CMake
- **Architecture**: SRP-compliant with MVVM pattern
- **Testing**: Qt Test framework

## Build Instructions

### Prerequisites
- Qt 6.2 or higher
- CMake 3.16 or higher
- C++17 compatible compiler (MSVC 2019+, GCC 9+, Clang 10+)

### Build Steps

#### Windows (MinGW)
```bash
# Clone repository
git clone https://github.com/paolosereno/LanScan.git
cd LanScan

# Clean build (recommended)
rm -rf build && mkdir build && cd build

# Configure with MinGW
cmake -G "MinGW Makefiles" -DCMAKE_BUILD_TYPE=Debug \
  -DCMAKE_PREFIX_PATH="C:/Qt/6.9.1/mingw_64" ..

# Build with 12 cores
cmake --build . -j12

# Run tests
ctest --output-on-failure

# Run application
./LanScan.exe
```

#### Windows (MSVC)
```bash
# Configure with MSVC
cmake -G "Visual Studio 17 2022" -A x64 \
  -DCMAKE_PREFIX_PATH="C:/Qt/6.9.1/msvc2022_64" ..

# Build Release
cmake --build . --config Release -j12
```

#### Linux
```bash
# Install dependencies
sudo apt-get install qt6-base-dev qt6-charts-dev cmake build-essential

# Configure and build
mkdir build && cd build
cmake -DCMAKE_BUILD_TYPE=Debug ..
cmake --build . -j$(nproc)

# Run tests
ctest --output-on-failure
```

## Development

- See [project.md](project.md) for detailed architecture and development roadmap
- See [TODO.md](TODO.md) for current task list and progress tracking

### Branch Strategy
- `main` - Production releases
- `develop` - Development branch
- `feature/phaseX-description` - Feature branches (X = 0-11)
- `bugfix/description` - Bug fixes
- `hotfix/description` - Critical fixes

### Commit Convention
```
[Phase X] Brief description

Detailed description of changes.

Location: src/path/to/files
```

## Project Status

**Current Phase**: Phase 5 - UI Foundation & Views ✅ **COMPLETED**
**Next Phase**: Phase 6 - Charts & Visualization
**Progress**: 50% (6/12 phases complete)
**Latest Release**: [v0.5.0-phase5](https://github.com/paolosereno/LanScan/releases/tag/v0.5.0-phase5)

### Recent Updates
- **2025-10-04**: Phase 5 completed - MVVM-based Qt GUI with ViewModels, Views, and custom delegates
- **2025-10-04**: Phase 4 completed - Application layer with multi-threaded controllers and management services
- **2025-10-04**: Phase 3 completed - Database persistence, export functionality, and settings management
- **2025-10-03**: Phase 2 completed - Added metrics calculation, ping service, and port scanning
- **2025-10-03**: Phase 1 completed - Implemented network discovery and IP scanning
- **2025-10-03**: Phase 0 completed - Project foundation and infrastructure

### Statistics
- **Files Created**: 158 total
- **Lines of Code**: ~14,000+
- **Test Coverage**: 15/19 tests passing (79% - 4 pre-existing failures)
- **Build Time**: ~35-40 seconds (Debug, 12 cores)
- **Executable Size**: 34 MB (Debug build)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributors

Paolo - Lead Developer
