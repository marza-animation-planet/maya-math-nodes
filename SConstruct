import excons
import excons.tools.maya as maya

maya.SetupMscver()

env = excons.MakeBaseEnv()

nameprefix = excons.GetArgument("name-prefix", "math_")
version = "1.5.1"

projs = [
   {
      "name": "mayaMathNodes",
      "type": "dynamicmodule",
      "ext": maya.PluginExt(),
      "prefix": "maya/plug-ins/%s" % maya.Version(nice=True),
      "bldprefix": maya.Version(),
      "defs": ["NODE_NAME_PREFIX=\\\"%s\\\"" % nameprefix,
               "PROJECT_VERSION=\\\"%s\\\"" % version],
      "incdirs": ["src"],
      "srcs": excons.glob("src/*.cpp"),
      "custom": [maya.Require],
      "install": {"maya/python": ["python/maya_math_nodes"]}
   }
]

excons.DeclareTargets(env, projs)