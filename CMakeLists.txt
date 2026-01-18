cmake_minimum_required(VERSION 3.5...4.2.1 FATAL_ERROR)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)

include(cmake/hunter/HunterInit.cmake)

project(lexilla VERSION 5.4.4 LANGUAGES CXX)

hunter_add_package(scintilla)

find_package(scintilla CONFIG REQUIRED)

set(HEADER_FILES
	include/Lexilla.h
	include/SciLexer.h
	access/LexillaAccess.h
	lexlib/Accessor.h
	lexlib/CatalogueModules.h
	lexlib/DefaultLexer.h
	lexlib/InList.h
	lexlib/LexAccessor.h
	lexlib/LexCharacterCategory.h
	lexlib/LexCharacterSet.h
	lexlib/LexerBase.h
	lexlib/LexerModule.h
	lexlib/LexerSimple.h
	lexlib/OptionSet.h
	lexlib/PropSetSimple.h
	lexlib/SparseState.h
	lexlib/StringCopy.h
	lexlib/StyleContext.h
	lexlib/SubStyles.h
	lexlib/WordList.h
)

set(SOURCE_FILES
	access/LexillaAccess.cxx
	lexers/LexA68k.cxx
	lexers/LexAbaqus.cxx
	lexers/LexAda.cxx
	lexers/LexAPDL.cxx
	lexers/LexAsciidoc.cxx
	lexers/LexAsm.cxx
	lexers/LexAsn1.cxx
	lexers/LexASY.cxx
	lexers/LexAU3.cxx
	lexers/LexAVE.cxx
	lexers/LexAVS.cxx
	lexers/LexBaan.cxx
	lexers/LexBash.cxx
	lexers/LexBasic.cxx
	lexers/LexBatch.cxx
	lexers/LexBibTeX.cxx
	lexers/LexBullant.cxx
	lexers/LexCaml.cxx
	lexers/LexCIL.cxx
	lexers/LexCLW.cxx
	lexers/LexCmake.cxx
	lexers/LexCOBOL.cxx
	lexers/LexCoffeeScript.cxx
	lexers/LexConf.cxx
	lexers/LexCPP.cxx
	lexers/LexCrontab.cxx
	lexers/LexCsound.cxx
	lexers/LexCSS.cxx
	lexers/LexD.cxx
	lexers/LexDart.cxx
	lexers/LexDataflex.cxx
	lexers/LexDiff.cxx
	lexers/LexDMAP.cxx
	lexers/LexDMIS.cxx
	lexers/LexECL.cxx
	lexers/LexEDIFACT.cxx
	lexers/LexEiffel.cxx
	lexers/LexErlang.cxx
	lexers/LexErrorList.cxx
	lexers/LexEScript.cxx
	lexers/LexFlagship.cxx
	lexers/LexForth.cxx
	lexers/LexFortran.cxx
	lexers/LexFSharp.cxx
	lexers/LexGAP.cxx
	lexers/LexGDScript.cxx
	lexers/LexGui4Cli.cxx
	lexers/LexHaskell.cxx
	lexers/LexHex.cxx
	lexers/LexHollywood.cxx
	lexers/LexHTML.cxx
	lexers/LexIndent.cxx
	lexers/LexInno.cxx
	lexers/LexJSON.cxx
	lexers/LexJulia.cxx
	lexers/LexKix.cxx
	lexers/LexKVIrc.cxx
	lexers/LexLaTeX.cxx
	lexers/LexLisp.cxx
	lexers/LexLout.cxx
	lexers/LexLua.cxx
	lexers/LexMagik.cxx
	lexers/LexMake.cxx
	lexers/LexMarkdown.cxx
	lexers/LexMatlab.cxx
	lexers/LexMaxima.cxx
	lexers/LexMetapost.cxx
	lexers/LexMMIXAL.cxx
	lexers/LexModula.cxx
	lexers/LexMPT.cxx
	lexers/LexMSSQL.cxx
	lexers/LexMySQL.cxx
	lexers/LexNim.cxx
	lexers/LexNimrod.cxx
	lexers/LexNix.cxx
	lexers/LexNsis.cxx
	lexers/LexNull.cxx
	lexers/LexOpal.cxx
	lexers/LexOScript.cxx
	lexers/LexPascal.cxx
	lexers/LexPB.cxx
	lexers/LexPerl.cxx
	lexers/LexPLM.cxx
	lexers/LexPO.cxx
	lexers/LexPOV.cxx
	lexers/LexPowerPro.cxx
	lexers/LexPowerShell.cxx
	lexers/LexProgress.cxx
	lexers/LexProps.cxx
	lexers/LexPS.cxx
	lexers/LexPython.cxx
	lexers/LexR.cxx
	lexers/LexRaku.cxx
	lexers/LexRebol.cxx
	lexers/LexRegistry.cxx
	lexers/LexRuby.cxx
	lexers/LexRust.cxx
	lexers/LexSAS.cxx
	lexers/LexScriptol.cxx
	lexers/LexSmalltalk.cxx
	lexers/LexSML.cxx
	lexers/LexSorcus.cxx
	lexers/LexSpecman.cxx
	lexers/LexSpice.cxx
	lexers/LexSQL.cxx
	lexers/LexStata.cxx
	lexers/LexSTTXT.cxx
	lexers/LexTACL.cxx
	lexers/LexTADS3.cxx
	lexers/LexTAL.cxx
	lexers/LexTCL.cxx
	lexers/LexTCMD.cxx
	lexers/LexTeX.cxx
	lexers/LexTOML.cxx
	lexers/LexTroff.cxx
	lexers/LexTxt2tags.cxx
	lexers/LexVB.cxx
	lexers/LexVerilog.cxx
	lexers/LexVHDL.cxx
	lexers/LexVisualProlog.cxx
	lexers/LexX12.cxx
	lexers/LexYAML.cxx
	lexers/LexZig.cxx
	lexlib/Accessor.cxx
	lexlib/DefaultLexer.cxx
	lexlib/InList.cxx
	lexlib/LexAccessor.cxx
	lexlib/LexCharacterCategory.cxx
	lexlib/LexCharacterSet.cxx
	lexlib/LexerBase.cxx
	lexlib/LexerModule.cxx
	lexlib/LexerSimple.cxx
	lexlib/PropSetSimple.cxx
	lexlib/StyleContext.cxx
	lexlib/WordList.cxx
	src/Lexilla.cxx
)

add_library(${PROJECT_NAME} STATIC ${HEADER_FILES} ${SOURCE_FILES})

target_include_directories(${PROJECT_NAME}
	PUBLIC
		$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
		$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/access>
		$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/lexlib>
		$<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}>
)

target_link_libraries(${PROJECT_NAME}
	PUBLIC
		scintilla::scintilla
)

include(GNUInstallDirs)

set(CONFIG_INSTALL_DIR "${CMAKE_INSTALL_LIBDIR}/cmake/${PROJECT_NAME}")
set(GENERATED_DIR "${CMAKE_CURRENT_BINARY_DIR}/generated")
set(VERSION_CONFIG "${GENERATED_DIR}/${PROJECT_NAME}ConfigVersion.cmake")
set(PROJECT_CONFIG "${GENERATED_DIR}/${PROJECT_NAME}Config.cmake")
set(TARGETS_EXPORT_NAME "${PROJECT_NAME}Targets")
set(NAMESPACE "${PROJECT_NAME}::")

include(CMakePackageConfigHelpers)

write_basic_package_version_file(
	"${VERSION_CONFIG}" COMPATIBILITY SameMajorVersion
)

configure_package_config_file(
	"cmake/Config.cmake.in"
	"${PROJECT_CONFIG}"
	INSTALL_DESTINATION "${CONFIG_INSTALL_DIR}"
)

install(
	TARGETS ${PROJECT_NAME}
	EXPORT "${TARGETS_EXPORT_NAME}"
	LIBRARY DESTINATION "${CMAKE_INSTALL_LIBDIR}"
	ARCHIVE DESTINATION "${CMAKE_INSTALL_LIBDIR}"
	RUNTIME DESTINATION "${CMAKE_INSTALL_BINDIR}"
	INCLUDES DESTINATION "${CMAKE_INSTALL_INCLUDEDIR}"
)

install(
	FILES ${HEADER_FILES}
	DESTINATION "${CMAKE_INSTALL_INCLUDEDIR}"
)

install(
	FILES "${PROJECT_CONFIG}" "${VERSION_CONFIG}"
	DESTINATION "${CONFIG_INSTALL_DIR}"
)

install(
	EXPORT "${TARGETS_EXPORT_NAME}"
	NAMESPACE "${NAMESPACE}"
	DESTINATION "${CONFIG_INSTALL_DIR}"
)
