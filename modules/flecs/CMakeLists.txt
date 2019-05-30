#-------------------------------------------------------------------------------
#   flecs module
#-------------------------------------------------------------------------------
fips_begin_module(flecs)
    # bake-util
    fips_src(bake/util/src NO_RECURSE)
    fips_src(bake/util/include NO_RECURSE)
    
    if (FIPS_POSIX)
    	fips_src(bake/util/src/posix)
    	fips_src(bake/util/include/bake-util/posix)
    elseif(FIPS_WIN)
    	fips_src(bake/util/src/win)
    	fips_src(bake/util/include/bake-util/win)
    endif()
    
    # flecs
    fips_src(flecs/src NO_RECURSE)
    fips_src(flecs/include NO_RECURSE)
    
    # flecs-util
    fips_src(flecs-util/src)
    fips_src(flecs-util/include)
	
	fips_include_directories(bake/util/include)
    fips_include_directories(flecs/include)
    fips_include_directories(flecs-util/include)
    
	add_definitions(-D__BAKE__)
    add_definitions(-DUT_IMPL)
fips_end_module()
