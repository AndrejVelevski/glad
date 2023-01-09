project(glad)

if (WIN32)
    add_library(${PROJECT_NAME}
        src/glad.c
        src/glad_wgl.c
    )
elseif(UNIX)
    add_library(${PROJECT_NAME}
    src/glad.c
    src/glad_glx.c
    )
elseif(APPLE) #not tested
    add_library(${PROJECT_NAME}
    src/glad.c
    src/glad_cgl.c
    )
else() #not tested
    add_library(${PROJECT_NAME}
    src/glad.c
    src/glad_egl.c
    )
endif()

target_include_directories(${PROJECT_NAME}
    PRIVATE include
)