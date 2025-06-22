cmake_minimum_required(VERSION 3.10)
project(TicTacToe)

set(CMAKE_CXX_STANDARD 17)

# Користувацький перемикач
option(USE_STATIC_LIB "Use static library instead of shared" ON)

# Додавання підкаталогу з бібліотекою
add_subdirectory(lib)

# Тип бібліотеки: статична або динамічна
if(USE_STATIC_LIB)
    set_target_properties(tictactoe_lib PROPERTIES LINKER_LANGUAGE CXX)
else()
    set_target_properties(tictactoe_lib PROPERTIES
        POSITION_INDEPENDENT_CODE ON
        LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib
    )
endif()

# Основний виконуваний файл
add_executable(TicTacToe main.cpp)

# Лінкування бібліотеки
target_link_libraries(TicTacToe PRIVATE tictactoe_lib)