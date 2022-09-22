# !!!DO NOT DO THIS IN ORCHESTRATOR FUNCTION!!!

## Must be deterministic

- Whole function will be "repeated"

## Do not use

- Current `DateTime`
- Generate random numbers or `GUIDS`
- Access data stores (e.g. database, configuration)

## Do

- Use `IDurableOrchestrationContext.CurrentUtcDateTime`
- Pass configuration into your orchestrator function (from starter function for example)
- Retrieve data in activity functions

## Must be non-blocking

- No I/O to disk or network
- No Thread.Sleep

## Do not initiate async operations

- Except on IDurableOrchestrationContext API
- No Task.Run, Task.Delay, HttpClient.SendAsync

## Do not create infinite loops

- Event history needs to be replayable
- ContinueAsNew should be used instead