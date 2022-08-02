![Data Warehouse architecture](https://github.com/colossalSorrow/data-warehouse-requirements-test-task/blob/master/DataWarehouse.png)
- Type entity stores all different types needed in the database. Parent_ID groups together different Types. For example Artifact is a parent of type Video.

Additional questions etc
1.	I would need more details to add fields to the enities.
2.	What does licensing mean in that sense? It will affect the License entity as well.
3.	How complex should the version control be?
4.	Is checksum used for integrity checking? If yes, then Artifact.Integrity_hash can be removed.
5.	Can an Artifact have many „parents“? If yes, then a new many-to-many relationship entity should be added.
6.	User authentication and communication with the database is done through cookies. For example cookie includes authenicated users ID and roles so the back-end can feed the system the information on the user that is currently doing operations. If artifact is checked for the owner the ID that is stored as an Owner_ID is compared against the cookie.
7.	Would it be okay to add a user type to the permission? Currently there is only one type of user (since administrator can access everything) that a permission can be assigned to but it might change in the future.
8.	How is it prefered to set up the communication between warehouses? Is it okay to do it via database? For example add a Warehouse_ID to the Artifact? Maybe add a centralized database  where all artifacts are connected to their warehouse ID? Or through an API endpoint which will ask for a specific artifact or for example all video type artifacts.
