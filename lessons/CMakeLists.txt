# Хелпер-функция: один .cpp -> один executable.
function(add_lesson_exe target_name source_file)
    add_executable(${target_name} ${source_file})
    target_link_libraries(${target_name} PRIVATE common_lib)
    target_compile_features(${target_name} PRIVATE cxx_std_14)

    if (MSVC)
        target_compile_options(${target_name} PRIVATE /W4)
    else()
        target_compile_options(${target_name} PRIVATE -Wall -Wextra -Wpedantic)
    endif()
endfunction()

# По мере добавления уроков исполняемые будут подтягиваться
# Позже накину флаги на сборку по модулям, чтобы не забивать ide миллионом таргетов
add_subdirectory(01_basics)