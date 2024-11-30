# Core Use-cases

## Activity Diagrams

### Add Photographer

```plantuml
@startuml

!define ThemePath https://azuker.github.io/sw-design/puml/theme
!includeurl ThemePath//usecases.puml

title Add Photographer

start
  :Apply for membership;
  :Verify application;
  if () then (Member exists)
    Error()
  else (Valid)
    :Process payment;
    :Approve;
  endif
stop

@enduml
```

### Request Photographer

```plantuml
@startuml

!define ThemePath https://azuker.github.io/sw-design/puml/theme
!includeurl ThemePath//usecases.puml

title Request Photographer

start
  :Request photographer;
  :Verify request;
  if () then (Not allowed)
    Error()
  else (OK)
    :Match photographer;
  endif
stop

@enduml
```

### Match Photographer

```plantuml
@startuml

!define ThemePath https://azuker.github.io/sw-design/puml/theme
!includeurl ThemePath//usecases.puml

title Match Photographer

start
  :Request match;
  :Verify request;
  if () then (Not allowed)
    Error()
  else (OK)
    :Analyze project needs;
    :Search candidates;
    :Assign best fit;
  endif
stop

@enduml
```

### Assign Photographer

```plantuml
@startuml

!define ThemePath https://azuker.github.io/sw-design/puml/theme
!includeurl ThemePath//usecases.puml

title Assign Photographer

start
  :Request assignment;
  :Verify request;
  if () then (Not allowed)
    label error_space
    label error_space
    label error_space
    label error_space
    label error
    Error()
  else (OK)
    :Verify availability;
    if () then (Not available)
      label sp_lab4
      goto error
    else (OK)
      :Assign to project;
    endif
  endif
stop

@enduml
```

### Terminate Photographer

```plantuml
@startuml

!define ThemePath https://azuker.github.io/sw-design/puml/theme
!includeurl ThemePath//usecases.puml

title Terminate Photographer

start
  :Request termination;
  :Verify request;
  if () then (Not allowed)
    Error()
  else (OK)
    :Terminate from active projects;
    :Make photographer available;
  endif
stop

@enduml
```

### Pay Photographer

```plantuml
@startuml

!define ThemePath https://azuker.github.io/sw-design/puml/theme
!include ThemePath//usecases-icons.puml
!include ThemePath//usecases.puml

title Pay Photographer

start
  fork
    :Find scheduled payments;
  fork again
    IconTimer()
  end fork {Scheduled Time >= Time}

  :Pay photographer;
stop

@enduml
```

### Create Project

```plantuml
@startuml

!define ThemePath https://azuker.github.io/sw-design/puml/theme
!includeurl ThemePath//usecases.puml

title Create Project

start
  :Request create project;
  :Verify request;
  if () then (Not allowed)
    Error()
  else (OK)
    :Add required abilities, skill level, location, duration, etc.;
    :Activate project;
  endif
stop

@enduml
```

### Close Project

```plantuml
@startuml

!define ThemePath https://azuker.github.io/sw-design/puml/theme
!includeurl ThemePath//usecases.puml

title Close Project

start
  :Request close project;
  :Verify request;
  if () then (Not allowed)
    Error()
  else (OK)
    :Release photographers;
    :Close project;
  endif
stop

@enduml
```
