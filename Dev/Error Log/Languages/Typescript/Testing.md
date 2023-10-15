
Running test won't run ended up being missing .js extension on one of my import 

Test used mocha command was 

npm run test -- -g "letterController POST"   

    "test": "npm run build && export FOR_TESTING=y && mocha --exit" 

Error [ERR_MODULE_NOT_FOUND]: Cannot find module '/home/jac/vsCodeProjects/work/tracflo-api-light/build/src/controllers/userController' imported from /home/jac/vsCodeProjects/work/tracflo-api-light/build/src/controllers/index.js 

    at new NodeError (node:internal/errors:372:5) 

    at finalizeResolution (node:internal/modules/esm/resolve:437:11) 

    at moduleResolve (node:internal/modules/esm/resolve:1009:10) 

    at defaultResolve (node:internal/modules/esm/resolve:1218:11) 

    at ESMLoader.resolve (node:internal/modules/esm/loader:580:30) 

    at ESMLoader.getModuleJob (node:internal/modules/esm/loader:294:18) 

    at ModuleWrap.<anonymous> (node:internal/modules/esm/module_job:80:40) 

    at link (node:internal/modules/esm/module_job:78:36)