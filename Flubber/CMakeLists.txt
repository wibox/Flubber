# CMakeList.txt: progetto CMake per Flubber. Includere l'origine e definire
# qui la logica specifica del progetto.
#
cmake_minimum_required (VERSION 3.8)

# Abilita Ricaricamento rapido per i compilatori MSVC, se supportato.
if (POLICY CMP0141)
  cmake_policy(SET CMP0141 NEW)
  set(CMAKE_MSVC_DEBUG_INFORMATION_FORMAT "$<IF:$<AND:$<C_COMPILER_ID:MSVC>,$<CXX_COMPILER_ID:MSVC>>,$<$<CONFIG:Debug,RelWithDebInfo>:EditAndContinue>,$<$<CONFIG:Debug,RelWithDebInfo>:ProgramDatabase>>")
endif()

project ("Flubber")

# Aggiungere l'origine all'eseguibile di questo progetto.
add_executable (Flubber "Flubber.cpp" "Flubber.h")

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET Flubber PROPERTY CXX_STANDARD 20)
endif()

# TODO: Aggiungere i test e, se necessario, installare le destinazioni.
