A data view is a declarative query and shape for OCS data. It includes the following components:

- **Index field**: Determines the primary index type and label of the index. The index must be a timestamp and displays in the first column of the data view.

- **Query**: Determines what data items are available for a data view. Queries can include streams or assets. A data view can have multiple queries.

- **Data field set**: Collections of fields originating from the same query.

- **Data view shape**: Determines if the data should be returned in the standard grouped row format or a narrow view, which is a pivot of the standard table.

Data views also include other components such as grouping instructions and default data range and interval.