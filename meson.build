project('doctest', 'cpp', 
    version : '1.2.9', 
    license : 'MIT', 
    default_options : ['cpp_std=c++14']
)
doctest_inc = include_directories('doctest')
fakeit_inc = include_directories('fakeit')
doctest_dep = declare_dependency(include_directories: [doctest_inc, fakeit_inc])

