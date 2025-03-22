add_subdirectory("integration")

Include(FetchContent)

FetchContent_Declare(
  Catch2
  GIT_REPOSITORY https://github.com/catchorg/Catch2.git
  GIT_TAG        v3.7.0 # or a later release
)

FetchContent_MakeAvailable(Catch2)

add_executable(tests test_ringbuffer.cpp)
target_link_libraries(tests PRIVATE Catch2::Catch2WithMain nuked-sc55-backend)
target_compile_features(tests PRIVATE cxx_std_23)
