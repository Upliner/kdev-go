set(completion_SRCS
    model.cpp
    worker.cpp
    context.cpp
    items/completionitem.cpp
    items/functionitem.cpp
    items/importcompletionitem.cpp
    completiondebug.cpp
    typematch.cpp
)

add_library(kdevgocompletion SHARED ${completion_SRCS})
generate_export_header(kdevgocompletion BASE_NAME kdevgocompletion EXPORT_MACRO_NAME KDEVGOCOMPLETION_EXPORT)
target_link_libraries(kdevgocompletion LINK_PRIVATE
    KDev::Language
    KDev::Interfaces
    KDev::Project
    kdevgoduchain
    kdevgoparser
)

install(TARGETS kdevgocompletion DESTINATION ${INSTALL_TARGETS_DEFAULT_ARGS})
