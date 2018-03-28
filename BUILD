load("@io_bazel_rules_scala//scala:scala.bzl", "scala_library", "scala_binary")
load("@io_bazel_rules_play_routes//play-routes:play-routes.bzl", "play_routes")

play_routes(
  name = "play-routes-basic",
  srcs = ["conf/routes"] + glob(["conf/*.routes"]),
  include_play_imports = True,
  generate_reverse_router = True,
)

scala_binary (
  name = "play-binary",
  main_class = "play.core.server.ProdServerStart",
  resources = ["conf/application.conf"],
  resource_strip_prefix = "conf",
  jvm_flags = [
    	"-Dhttp.port=9000",
    	"-Dapplication.name=foo-service",
  ],
  srcs = glob(["app/**/*.scala"]) + [
    ":play-routes-basic",
  ],
  deps = [
    "@com_github_scopt_scopt_2_11//jar",
    "@scala//:scala-library",
    "@scala//:scala-parser-combinators",
    "@scala//:scala-reflect",
    "@aopalliance_aopalliance//jar",
    "@ch_qos_logback_logback_classic//jar",
    "@ch_qos_logback_logback_core//jar",
    "@com_chuusai_shapeless//jar",
    "@com_fasterxml_jackson_core_jackson_annotations//jar",
    "@com_fasterxml_jackson_core_jackson_core//jar",
    "@com_fasterxml_jackson_core_jackson_databind//jar",
    "@com_fasterxml_jackson_datatype_jackson_datatype_jdk8//jar",
    "@com_fasterxml_jackson_datatype_jackson_datatype_jsr310//jar",
    "@com_google_code_findbugs_jsr305//jar",
    "@com_google_guava_guava//jar",
    "@com_google_inject_extensions_guice_assistedinject//jar",
    "@com_google_inject_extensions_guice_multibindings//jar",
    "@com_google_inject_guice//jar",
    "@com_netaporter_scala_uri//jar",
    "@com_typesafe_akka_akka_actor//jar",
    "@com_typesafe_akka_akka_slf4j//jar",
    "@com_typesafe_akka_akka_stream//jar",
    "@com_typesafe_netty_netty_reactive_streams_http//jar",
    "@com_typesafe_netty_netty_reactive_streams//jar",
    "@com_typesafe_play_build_link//jar",
    "@com_typesafe_play_play_datacommons//jar",
    "@com_typesafe_play_play_exceptions//jar",
    "@com_typesafe_play_play_functional//jar",
    "@com_typesafe_play_play_iteratees//jar",
    "@com_typesafe_play_play_json//jar",
    "@com_typesafe_play_play_logback//jar",
    "@com_typesafe_play_play_netty_server//jar",
    "@com_typesafe_play_play_netty_utils//jar",
    "@com_typesafe_play_play_server//jar",
    "@com_typesafe_play_play_streams//jar",
    "@com_typesafe_play_play_2_11//jar",
    "@com_typesafe_play_twirl_api_2_11//jar",
    "@com_typesafe_config//jar",
    "@com_typesafe_ssl_config_core//jar",
    "@commons_codec_commons_codec//jar",
    "@io_netty_netty_buffer//jar",
    "@io_netty_netty_codec_http//jar",
    "@io_netty_netty_codec//jar",
    "@io_netty_netty_common//jar",
    "@io_netty_netty_handler//jar",
    "@io_netty_netty_transport_native_epoll//jar",
    "@io_netty_netty_transport//jar",
    "@io_spray_spray_json//jar",
    "@javax_inject_javax_inject//jar",
    "@javax_transaction_jta//jar",
    "@joda_time_joda_time//jar",
    "@net_codingwell_scala_guice//jar",
    "@org_apache_commons_commons_lang3//jar",
    "@org_joda_joda_convert//jar",
    "@org_parboiled_parboiled//jar",
    "@org_reactivestreams_reactive_streams//jar",
    "@org_scala_lang_modules_scala_java8_compat//jar",
    "@org_scala_lang_modules_scala_parser_combinators//jar",
    "@org_scala_lang_modules_scala_xml//jar",
    "@org_scala_lang_scala_reflect//jar",
    "@org_scala_stm_scala_stm//jar",
    "@org_slf4j_jcl_over_slf4j//jar",
    "@org_slf4j_jul_to_slf4j//jar",
    "@org_slf4j_slf4j_api//jar",
    "@xerces_xercesImpl//jar",
    "@xml_apis_xml_apis//jar"
  ]
)