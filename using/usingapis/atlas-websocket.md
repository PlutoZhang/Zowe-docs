# Using explorer server WebSocket services

The explorer server provides WebSocket services that can be accessed by using the WSS scheme. With explorer server WebSocket services, you can view the system log in the System log UI that is refreshed automatically when messages are written. You can also open a JES spool file for an active job and view its contents that refresh through a web socket.

| Server Endpoint | Description | Prerequisites |
| --- | --- | --- |
| `/api/sockets/jobs/{jobname}/ids/{jobid}/files/{fileid}` | Tail the output of an active job. Use this WSS endpoint to read the tail of an active job's output file in real time. | z/OSMF restjobs |

