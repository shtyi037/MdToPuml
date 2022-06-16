```plantuml
@startuml table

map tb_shipper {
 id => int 
 name => varchar
 mail => varchar
 account => varchar
 info=> varchar
 type_id=> int
 key=> varchar
 remark=> varchar
 create_date=> datetime
 update_date=> datetime
}

map tb_receiver {
 id => int
 name => varchar
 mail => varchar
 account => varchar
 info=> varchar
 type_id=> int
 state=> varchar
 remark=> varchar
 create_date=> datetime
 update_date=> datetime
}

map tb_type{
 id => int
 headers=> varchar
 name => varchar
 state=> varchar
 create_date=> datetime
 update_date=> datetime
}


map log_message {
 id => int
 subject=> varchar
 shipper_id=> int 
 type_id=> int
 recever_id=> varchar
 content=> varchar
 attachment=> varchar
 remark=> varchar
 sender_date=> datetime
 typeId => int
}

tb_shipper::type_id-->tb_type::id

tb_receiver::type_id-->tb_type::id

log_message::shipper_id -->tb_shipper::id
log_message::recever_id -->tb_receiver::id
log_message::type_id -->tb_type::id

@enduml
```puml