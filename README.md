# Download-RDL-file-SSRS-report-for-Task-sequence-Pre-Cache-status
Download RDL file to get the Task sequence pre-cache information. You will get prompt to select Task sequence and collection.  Import it to your SSRS server. That is it. You are done. Run the report and you will get result as shown below.  Make sure Custom MOF is included in your inventory to collection Client Cache information. Download MOF file from 
More details https://www.anoopcnair.com/custom-inventory-for-task-sequence-client-side-pre-cache-status-part-2/


Collection Query 

SELECT aa.Netbios_Name0,bb.ContentId0,bb.ContentSize0,bb.Location0 from v_R_System aa left join v_GS_CACHEINFOEX bb on aa.ResourceID=bb.ResourceID join
v_FullCollectionMembership cc on bb.ResourceID in (Select cc.ResourceID from v_FullCollectionMembership where cc.CollectionID ='CHQ00017')
