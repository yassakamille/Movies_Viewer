# 1= Sign-Up-System
## Using ROOM Database
### Sign up-Log in system that allows users to create their username and password and then use them to log in to the Application :
<img src="https://github.com/yassakamille/Sign-Up-System/assets/85362073/287629f2-e10c-4960-88f2-dcba9eaa0cc7" width="250" height="400"/>
<br/>
<h3 >if Username or password is worng </h3>
<img src = "https://github.com/yassakamille/Sign-Up-System/assets/85362073/7d10717e-caf4-43a9-89b2-5962be98b8f2" width=" 250" height="475"/>
<br/>
 <h3>User Can register</h3> 
<img src = "https://github.com/yassakamille/Sign-Up-System/assets/85362073/9e9c1379-96a6-448a-abdc-731c33c7ce96" width="250" height="475"/>
<br/>
<img src = "https://github.com/yassakamille/Sign-Up-System/assets/85362073/df20d3e3-deda-46b5-a628-0a797d958451" width="250" height="475"/>
<br/>
<h3>Then he can log in to the application</h3>
<br/>
<img src = "https://github.com/yassakamille/Sign-Up-System/assets/85362073/fed73e30-d8a1-4cdc-a178-6caa9d9e2433" width="250" height="475"/>
<br/>
<img src = "https://github.com/yassakamille/Sign-Up-System/assets/85362073/1003b3f3-eecd-420d-9a23-5676709a1fd3" width="250" height="475"/>
<br/>

[![Architecture diagram of yassakamille/movies_viewer](https://gitdiagram.com/yassakamille/movies_viewer/diagram.png)](https://gitdiagram.com/yassakamille/movies_viewer?utm_source=readme&utm_medium=picture)


## Movies Viewer — Project Architecture

```mermaid id="k5v2nr"
flowchart TD

subgraph group_accounts["Account Screens"]
  node_login["Login Screen<br/>MainActivity.java"]
  node_registration["Registration Screen<br/>RegistraitionActivity.java"]
end

subgraph group_storage["Room Storage"]
  node_database[("User Database<br/>UserDatabase.java")]
  node_dao["User DAO<br/>userdao.java"]
  node_user_entity["User Entity<br/>user.java"]
end

subgraph group_movies["Movie Browsing"]
  node_movie_screen["Movie Screen<br/>StartActivity.java"]
  node_adapter["Movie List Adapter<br/>AdvancedRecycleAdapter.java"]
end

subgraph group_movie_data["Movie Data"]
  node_movie_service["Movie API Client<br/>MovieService.java"]
  node_movie_response["Movie Response<br/>MoviesModel.java"]
  node_movie["Movie Record<br/>Movie.java"]
end

node_person(("App User"))
node_movie_api{{"Movie API"}}
node_image_host{{"Poster Image Host"}}

node_person -->|"enters credentials"| node_login
node_person -->|"registers"| node_registration

node_login -->|"accesses"| node_database
node_registration -->|"accesses"| node_database
node_database -->|"provides access to"| node_dao
node_dao -->|"manages"| node_user_entity

node_login -->|"login succeeds"| node_movie_screen
node_movie_screen -->|"calls"| node_movie_service
node_movie_service -->|"requests movies"| node_movie_api
node_movie_api -->|"returns movie data"| node_movie_service
node_movie_service -->|"provides response"| node_movie_response
node_movie_response -->|"contains records"| node_movie
node_movie_screen -->|"updates list"| node_adapter
node_adapter -->|"renders records"| node_movie
node_adapter -->|"loads posters"| node_image_host

click node_login "https://github.com/yassakamille/movies_viewer/blob/main/app/src/main/java/com/apps/myapplication1/MainActivity.java"
click node_registration "https://github.com/yassakamille/movies_viewer/blob/main/app/src/main/java/com/apps/myapplication1/RegistraitionActivity.java"
click node_database "https://github.com/yassakamille/movies_viewer/blob/main/app/src/main/java/com/apps/myapplication1/UserDatabase.java"
click node_dao "https://github.com/yassakamille/movies_viewer/blob/main/app/src/main/java/com/apps/myapplication1/userdao.java"
click node_user_entity "https://github.com/yassakamille/movies_viewer/blob/main/app/src/main/java/com/apps/myapplication1/user.java"
click node_movie_screen "https://github.com/yassakamille/movies_viewer/blob/main/app/src/main/java/com/apps/myapplication1/StartActivity.java"
click node_adapter "https://github.com/yassakamille/movies_viewer/blob/main/app/src/main/java/com/apps/myapplication1/AdvancedRecycleAdapter.java"
click node_movie_service "https://github.com/yassakamille/movies_viewer/blob/main/app/src/main/java/com/apps/myapplication1/MovieService.java"
click node_movie_response "https://github.com/yassakamille/movies_viewer/blob/main/app/src/main/java/com/apps/myapplication1/MoviesModel.java"
click node_movie "https://github.com/yassakamille/movies_viewer/blob/main/app/src/main/java/com/apps/myapplication1/Movie.java"

classDef toneNeutral fill:#f8fafc,stroke:#334155,stroke-width:1.5px,color:#0f172a
classDef toneBlue fill:#dbeafe,stroke:#2563eb,stroke-width:1.5px,color:#172554
classDef toneAmber fill:#fef3c7,stroke:#d97706,stroke-width:1.5px,color:#78350f
classDef toneMint fill:#dcfce7,stroke:#16a34a,stroke-width:1.5px,color:#14532d
classDef toneRose fill:#ffe4e6,stroke:#e11d48,stroke-width:1.5px,color:#881337
classDef toneIndigo fill:#e0e7ff,stroke:#4f46e5,stroke-width:1.5px,color:#312e81
classDef toneTeal fill:#ccfbf1,stroke:#0f766e,stroke-width:1.5px,color:#134e4a

class node_login,node_registration,node_person toneBlue
class node_database,node_dao,node_user_entity toneAmber
class node_movie_screen,node_adapter toneMint
class node_movie_service,node_movie_response,node_movie toneRose
class node_movie_api,node_image_host toneIndigo
```

[![Architecture diagram](https://gitdiagram.com/diagram-badge.svg)](https://gitdiagram.com/yassakamille/movies_viewer?utm_source=readme&utm_medium=badge)

