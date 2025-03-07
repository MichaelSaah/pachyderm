# Datum

A datum is the smallest indivisible unit of computation within a
A job can have one, many or no datums. Each datum is processed
independently with a single execution of the user code and
then the results of all the datums are merged together to
create the final output commit.

The number of datums for a job is defined by the [glob pattern]
(glob-pattern.md) which you specify for each input. Think of
datums as if you were telling Pachyderm how to divide your
input data to efficiently distribute computation and
only process the *new* data. You can configure a whole
input repository to be one datum, each top-level filesystem object
to be a separate datum, specific paths can be datums,
and so on. Datums affect how Pachyderm distributes processing workloads
and are instrumental in optimizing your configuration for best performance.

Pachyderm takes each datum and processes it in isolation on one of
the pipeline worker nodes. You can define datums, workers, and other
performance parameters can all be configured through the
corresponding fields in the [pipeline specification](../../../reference/pipeline_spec.md).

To understand how datums affect data processing in Pachyderm, you need to
understand the following subconcepts:

* [Glob Pattern](glob-pattern.md)
* [Datum Processing](relationship-between-datums.md)
