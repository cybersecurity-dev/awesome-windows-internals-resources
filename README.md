<div align="center">
    <p align="center">
        <a href="https://github.com/cybersecurity-dev/awesome-windows-internals">
          <img width="20%" src="https://github.com/cybersecurity-dev/cybersecurity-dev/blob/main/assets/Windows.svg" />
        </a>
    </p>

```mermaid
flowchart TB
    subgraph USER["User Mode"]
        UAPP["User Applications"]
        SVC["Windows Services"]
        ENV["Environment Subsystems"]
        DLL["Subsystem DLLs"]
        NTDLL["NTDLL"]
    end

    subgraph TRANSITION["System-Call Boundary"]
        STUB["System-Call Stubs"]
        SSDT["System-Service Dispatch"]
    end

    subgraph KMODE["Kernel Mode"]
        subgraph EXECUTIVE["Windows Executive"]
            OM["Object Manager"]
            PM["Process Manager"]
            MM["Memory Manager"]
            IO["I/O Manager"]
            CM["Configuration Manager"]
            SRM["Security Reference Monitor"]
            ALPC["ALPC"]
        end

        subgraph CORE["Windows Kernel"]
            SCHED["Thread Scheduler"]
            TRAP["Trap and Exception Handling"]
            INT["Interrupt Dispatching"]
            SYNC["Kernel Synchronization"]
            DPCAPC["DPC and APC"]
        end

        subgraph DRIVER_LAYER["Kernel Drivers"]
            FSD["File-System Drivers"]
            NET["Network Drivers"]
            FILTER["Filter Drivers"]
            DEVICE["Device Drivers"]
        end

        HAL["Hardware Abstraction Layer"]
    end

    subgraph PHYSICAL["Hardware"]
        CPU["CPU and Interrupt Controllers"]
        MEM["Physical Memory"]
        DISK["Storage Devices"]
        NIC["Network Devices"]
        PERIPH["Peripheral Devices"]
    end

    UAPP --> DLL
    SVC --> DLL
    ENV --> DLL
    DLL --> NTDLL
    NTDLL --> STUB
    STUB --> SSDT

    SSDT --> OM
    SSDT --> PM
    SSDT --> MM
    SSDT --> IO
    SSDT --> SRM

    PM --> SCHED
    MM --> CORE
    IO --> DRIVER_LAYER
    SRM --> OM
    ALPC --> PM

    FSD --> DEVICE
    NET --> DEVICE
    FILTER --> FSD
    DRIVER_LAYER --> HAL

    HAL --> CPU
    HAL --> MEM
    HAL --> DISK
    HAL --> NIC
    HAL --> PERIPH

    classDef user fill:#e3f2fd,color:#111,stroke:#1e88e5
    classDef transition fill:#fff8e1,color:#111,stroke:#f9a825
    classDef executive fill:#e8f5e9,color:#111,stroke:#43a047
    classDef kernel fill:#fff3e0,color:#111,stroke:#ef6c00
    classDef driver fill:#f3e5f5,color:#111,stroke:#8e24aa
    classDef hal fill:#ffebee,color:#111,stroke:#e53935
    classDef hardware fill:#eceff1,color:#111,stroke:#546e7a

    class UAPP,SVC,ENV,DLL,NTDLL user
    class STUB,SSDT transition
    class OM,PM,MM,IO,CM,SRM,ALPC executive
    class SCHED,TRAP,INT,SYNC,DPCAPC kernel
    class FSD,NET,FILTER,DEVICE driver
    class HAL hal
    class CPU,MEM,DISK,NIC,PERIPH hardware
```

# **`Awesome`** Windows Internals Resources [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
</div>

[![YouTube](https://img.shields.io/badge/YouTube-%23FF0000.svg?style=for-the-badge&logo=YouTube&logoColor=white)]() 
[![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)]()

<p align="center">
    <a href="https://github.com/cybersecurity-dev/"><img height="25" src="https://github.com/cybersecurity-dev/cybersecurity-dev/blob/main/assets/github.svg" alt="GitHub"></a>
    &nbsp;
    <a href="https://www.youtube.com/@CyberThreatDefence"><img height="25" src="https://github.com/cybersecurity-dev/cybersecurity-dev/blob/main/assets/youtube.svg" alt="YouTube"></a>
    &nbsp;
    <a href="https://cyberthreatdefence.com/my_awesome_lists"><img height="20" src="https://github.com/cybersecurity-dev/cybersecurity-dev/blob/main/assets/blog.svg" alt="My Awesome Lists"></a>
    <img src="https://github.com/cybersecurity-dev/cybersecurity-dev/blob/main/assets/bar.gif">
</p>

## 📖 Contents
- [Books](#books)
- [Videos](#videos)
- [My Other Awesome Lists](#my-other-awesome-lists)
- [Contributing](#contributing)
- [Contributors](#contributors)

### Books
* [Windows Internals: System architecture, processes, threads, memory management, and more, Part 1 (Developer Reference)](https://www.amazon.com/Windows-Internals-Part-architecture-management/dp/0735684189)
* [Windows Internals, Part 2 (Developer Reference)](https://www.amazon.com/Windows-Internals-Part-2-7th/dp/0135462401)
* [Windows Security Internals: A Deep Dive into Windows Authentication, Authorization, and Auditing](https://www.amazon.com/Windows-Security-Internals-Authentication-Authorization/dp/1718501986)

### Videos

##

### My Other Awesome Lists
You can access the my other awesome lists [here](https://cyberthreatdefence.com/my_awesome_lists)

### Contributing
[Contributions of any kind welcome, just follow the guidelines](contributing.md)!

### Contributors
[Thanks goes to these contributors](https://github.com/cybersecurity-dev/awesome-windows-internals-resources/graphs/contributors)!

### License
[![CC0](http://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](http://creativecommons.org/publicdomain/zero/1.0)

[🔼 Back to top](#awesome-windows-internals-resources-)
