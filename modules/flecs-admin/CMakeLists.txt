#-------------------------------------------------------------------------------
#   flecs-admin module
#-------------------------------------------------------------------------------
fips_begin_module(flecs-admin)
    # flecs-components-http
    fips_src(flecs-components-http/src)
    fips_src(flecs-components-http/include)
    
    # flecs-systems-admin
    fips_src(flecs-systems-admin/src)
    fips_src(flecs-systems-admin/include)
    
    # flecs-systems-civetweb
    fips_src(flecs-systems-civetweb/src)
    fips_src(flecs-systems-civetweb/include)
    
    # flecs base includes
    fips_include_directories(../flecs/flecs/include)
    fips_include_directories(../flecs/flecs-util/include)
    fips_include_directories(../flecs/bake/util/include)
    
    # flecs admin includes
    fips_include_directories(flecs-components-http/include)
    fips_include_directories(flecs-systems-admin/include)
    fips_include_directories(flecs-systems-civetweb/include)
    
	fips_deps(flecs)
	add_definitions(-D__BAKE__)
    add_definitions(-DUT_IMPL)
    add_definitions(-DBAKE_PROJECT_ID=\"flecs.systems.admin\")
fips_end_module()