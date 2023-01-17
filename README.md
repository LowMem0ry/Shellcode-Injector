# What is Process Injection
* Process injection is a technique of running malicious code in the address space of separate processes. After the malicious code is injected into a legitimate process, attackers can access legitimate processes' resources such as process memory, system/network resources, and elevated privileges.

# Technical Details(in high level)
* open the target process with PROCESS_ALL_ACCESS using OpenProcess()
* allocate memory inside the target process using VirtualAllocEx()
* copy the buffer into the allocated memory of the target process using WriteProcessMemory()
* start a thread to execute the buffer CreateRemoteThread()
* wait the thread to finish WaitForSingleObject()
## all these functions are documented in MSDN
- [OpenProcess()](https://learn.microsoft.com/en-us/windows/win32/api/processthreadsapi/nf-processthreadsapi-openprocess)

- [VirtualAllocEx()](https://learn.microsoft.com/en-us/windows/win32/api/memoryapi/nf-memoryapi-virtualallocex)

- [WriteProcessMemory()](https://learn.microsoft.com/en-us/windows/win32/api/memoryapi/nf-memoryapi-writeprocessmemory)

- [CreateRemoteThread()](https://learn.microsoft.com/en-us/windows/win32/api/processthreadsapi/nf-processthreadsapi-createremotethread)

- [WaitForSingleObject()](https://learn.microsoft.com/en-us/windows/win32/api/synchapi/nf-synchapi-waitforsingleobject)

# DEMO
![Alt Text](https://github.com/Zextus/Shellcode-Injector/blob/main/demo.gif)
