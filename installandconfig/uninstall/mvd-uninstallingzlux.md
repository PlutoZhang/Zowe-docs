# Uninstalling zLUX

1. The zLUX server is run under the ZOESVR started task, so it should terminate when ZOESVR is stopped. If it does not, use one of the following standard process signals to stop the server:
   * SIGHUP
   * SIGTERM
   * SIGKILL
2. Delete the original folders \(except in the case where you have customized the installation to point to folders other than the original folders\).

