---
author: themar-msft;hajya
ms.date: 09/30/2019
---

# Factory Orchestrator

Factory Orchestrator provides a simple and reliable way to run and manage factory line validation and fault analysis workflows. Beyond the factory floor Factory Orchestrator can be during os and hardware development to support various developer inner-loop and diagnostics activities.

Factory Orchestrator consists of two components:

- A system service (FactoryOrchestratorService.exe): The service tracks task information, including run unique per-run results and logging; even persisting task state to allow the service to be resilient to data loss due to client failure.

- A UWP app: Communicates with the service to run executable tasks and commands on a device under test (DUT). This app can communicate with the service running  on the same device and/or over a network.

Tasks are used to capture actions that the server can executre, and TaskLists are used to organize and manage these Tasks. Learn more about [Tasks and Tasklists](tasks-and-tasklists.md)

[Getting started with Factory Orchestrator](get-started-with-factory-orchestrator.md)

## Factory Orchestrator logs

By default, the Factory Orchestrator Service generates log files in the following location on the test device: `%ProgramData%\FactoryOrchestrator`.

### Factory Orchestrator Service log file

The service log file contains details about the operation of the Factory Orchestrator Service. It is always found at `%ProgramData%\FactoryOrchestrator\FactoryOrchestratorService.log` on a device. Inspect this log for details about the service's operation.

### Factory Orchestrator Task log files

The Task log files contain details about the execution of a specific of the Factory Orchestrator Task. There is one log file generated for each run of a Task. The files are saved to `%ProgramData%\FactoryOrchestrator\Logs\` on a device by default, but this location can be changed using the FactoryOrchestratorClient.SetLogFolder() API. Use the FactoryOrchestratorClient.GetLogFolder() API to programmatically retrieve the log folder.
