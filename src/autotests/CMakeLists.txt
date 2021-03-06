include(ECMMarkAsTest)
include(ECMMarkNonGuiExecutable)

set(EXECUTABLE_OUTPUT_PATH ${CMAKE_CURRENT_BINARY_DIR})

set(KONSOLE_TEST_LIBS Qt5::Test konsoleprivate)

add_executable(CharacterColorTest CharacterColorTest.cpp)
ecm_mark_as_test(CharacterColorTest)
ecm_mark_nongui_executable(CharacterColorTest)
add_test(CharacterColorTest CharacterColorTest)
target_link_libraries(CharacterColorTest ${KONSOLE_TEST_LIBS})

add_executable(CharacterWidthTest CharacterWidthTest.cpp)
ecm_mark_as_test(CharacterWidthTest)
ecm_mark_nongui_executable(CharacterWidthTest)
add_test(CharacterWidthTest CharacterWidthTest)
target_link_libraries(CharacterWidthTest ${KONSOLE_TEST_LIBS})


if (NOT ${CMAKE_SYSTEM_NAME} MATCHES "Darwin")
    add_executable(DBusTest DBusTest.cpp)
    ecm_mark_as_test(DBusTest)
    add_test(DBusTest DBusTest)
    target_link_libraries(DBusTest ${KONSOLE_TEST_LIBS} Qt5::DBus)
endif()

add_executable(HistoryTest HistoryTest.cpp)
ecm_mark_as_test(HistoryTest)
ecm_mark_nongui_executable(HistoryTest)
add_test(HistoryTest HistoryTest)
target_link_libraries(HistoryTest ${KONSOLE_TEST_LIBS} KF5::Parts)

add_executable(KeyboardTranslatorTest KeyboardTranslatorTest.cpp)
ecm_mark_as_test(KeyboardTranslatorTest)
ecm_mark_nongui_executable(KeyboardTranslatorTest)
add_test(KeyboardTranslatorTest KeyboardTranslatorTest)
target_link_libraries(KeyboardTranslatorTest ${KONSOLE_TEST_LIBS})

if (NOT ${CMAKE_SYSTEM_NAME} MATCHES "Darwin")
    add_executable(PartTest PartTest.cpp)
    ecm_mark_as_test(PartTest)
    add_test(PartTest PartTest)
    target_link_libraries(PartTest KF5::XmlGui KF5::Parts KF5::Pty
                               ${KONSOLE_TEST_LIBS})
endif()

add_executable(ProfileTest ProfileTest.cpp)
ecm_mark_as_test(ProfileTest)
ecm_mark_nongui_executable(ProfileTest)
add_test(ProfileTest ProfileTest)
target_link_libraries(ProfileTest ${KONSOLE_TEST_LIBS})

add_executable(PtyTest PtyTest.cpp)
ecm_mark_as_test(PtyTest)
ecm_mark_nongui_executable(PtyTest)
add_test(PtyTest PtyTest)
target_link_libraries(PtyTest KF5::Pty ${KONSOLE_TEST_LIBS})

add_executable(SessionTest SessionTest.cpp)
ecm_mark_as_test(SessionTest)
ecm_mark_nongui_executable(SessionTest)
add_test(SessionTest SessionTest)
target_link_libraries(SessionTest ${KONSOLE_TEST_LIBS} KF5::Parts)

add_executable(ShellCommandTest ShellCommandTest.cpp)
ecm_mark_as_test(ShellCommandTest)
ecm_mark_nongui_executable(ShellCommandTest)
add_test(ShellCommandTest ShellCommandTest)
target_link_libraries(ShellCommandTest ${KONSOLE_TEST_LIBS})

add_executable(TerminalCharacterDecoderTest
               TerminalCharacterDecoderTest.cpp)
ecm_mark_as_test(TerminalCharacterDecoderTest)
ecm_mark_nongui_executable(TerminalCharacterDecoderTest)
add_test(TerminalCharacterDecoderTest TerminalCharacterDecoderTest)
target_link_libraries(TerminalCharacterDecoderTest ${KONSOLE_TEST_LIBS})

add_executable(TerminalTest TerminalTest.cpp)
ecm_mark_as_test(TerminalTest)
ecm_mark_nongui_executable(TerminalTest)
add_test(TerminalTest TerminalTest)
target_link_libraries(TerminalTest ${KONSOLE_TEST_LIBS} KF5::Parts)

add_executable(TerminalInterfaceTest TerminalInterfaceTest.cpp)
ecm_mark_as_test(TerminalInterface)
add_test(TerminalInterfaceTest TerminalInterfaceTest)
target_link_libraries(TerminalInterfaceTest
                      KF5::Parts
                      ${KONSOLE_TEST_LIBS})

add_executable(Vt102EmulationTest Vt102EmulationTest.cpp)
ecm_mark_as_test(Vt102EmulationTest)
ecm_mark_nongui_executable(Vt102EmulationTest)
add_test(Vt102EmulationTest Vt102EmulationTest)
target_link_libraries(Vt102EmulationTest ${KONSOLE_TEST_LIBS})

