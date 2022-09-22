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