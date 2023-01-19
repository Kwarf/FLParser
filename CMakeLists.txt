cmake_minimum_required(VERSION 3.11)

project(Monad.FLParser LANGUAGES CSharp)

cmake_policy(SET CMP0057 NEW)
include(CSharpUtilities)

# Note: The space suffix is required for the flag to work correctly.
set(CMAKE_CSharp_FLAGS "/langversion:latest ")

set(MONAD_FL_PARSER_SOURCES
	Properties/AssemblyInfo.cs

	AutomationData.cs
	AutomationKeyframe.cs
	Channel.cs
	ChannelPlaylistItem.cs
	Enums.cs
	FlParseException.cs
	GeneratorData.cs
	IChannelData.cs
	Insert.cs
	InsertSlot.cs
	IPlaylistItem.cs
	Note.cs
	Pattern.cs
	PatternPlaylistItem.cs
	Plugin.cs
	PluginIoInfo.cs
	Project.cs
	ProjectParser.cs
	Track.cs
)

add_library(Monad.FLParser SHARED ${MONAD_FL_PARSER_SOURCES})
set_property(TARGET Monad.FLParser PROPERTY VS_DOTNET_TARGET_FRAMEWORK_VERSION "v4.6.1")
set_property(TARGET Monad.FLParser PROPERTY VS_DOTNET_REFERENCES 
	"System"
	"System.Core"
)
install(TARGETS Monad.FLParser DESTINATION bin)
