project('credui', 'cpp',
  version : '0.1',
  default_options : ['warning_level=3',
   'cpp_std=c++17',
   'default_library=both'
    ])

# Define a project root for installation
dependencies = []

cmake = import('cmake')



imgui_subproj = subproject('imgui')
imgui_dep = imgui_subproj.get_variable('imgui_dep')

dependencies += imgui_dep

dependencies += cmake.subproject('glfw').dependency('glfw3')



exe = executable('credui', './src/credui.cpp',
  dependencies : dependencies,
  link_args: ['-lopengl32','/NODEFAULTLIB:msvcrt'],
  install : true,
  )

test('basic', exe)
