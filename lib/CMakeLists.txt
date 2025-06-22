add_library(tictactoe_lib
    afterGameMenu.cpp
    displayBoard.cpp
    isBoardFull.cpp
    isWin.cpp
    loadSettings.cpp
    mainMenu.cpp
    playGame.cpp
    saveGameResult.cpp
    saveSettings.cpp
    settingsMenu.cpp
    showHistory.cpp
)

target_include_directories(tictactoe_lib PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})