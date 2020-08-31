# peering_class_config

##Classes
collect_as_paths
modules:
  aspathentries  
view_configurations
modules:
  check_configurations # takes a dictionary as a parameter
peering_configurations # currently not in use
peering_pe_data
modules:
  instantiation
  junos_configs
  nxos_configs
  ios_configs
  
#Operation

##Create a collect_as_paths object
collect_as_paths_object=collect_as_paths()

##get an array of as paths entries stored in as_paths
as_paths=collect_as_paths_object.aspathentries()

##Create a view_configurations object to validate configurations to be created per device
v=view_configurations()

##Call the check_configurations module of the v object, input parameter is as_paths from step 2 above
configs_view=v.check_configurations(as_paths)

##Create the peering_pe_data object, input parameter is as_paths from step 2 above
peering_pe_data_object=peering_pe_data(as_paths)

##Push ios configurations
Call ios_configs module to push ios configurations
peering_pe_data_object.ios_configs()

##Push nxos configurations
Call ios_configs module to push ios configurations
peering_pe_data_object.nxos_configs()

##Push juniper configurations
Call junos_configs module to push ios configurations
peering_pe_data_object.junos_configs()









  
  
  
  









