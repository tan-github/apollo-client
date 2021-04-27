# apollo-client
apollo客户端

$config_server = 'http://192.168.1.236:30005';
$app_id = 'zsy-test';
$namespaces = array('application');
//项目配置目录
$config_path = './config';
//集群
$env = 'testing';
$apollo = new \Apollo\Client\ApolloClient($config_server, $app_id, $namespaces);
$apollo->setCluster($env);
$apollo->setSaveDir($config_path);
$error_msg = $apollo->start();

if ($error_msg) {
    echo 'Apollo配置更新失败，错误信息：'.$error_msg . PHP_EOL;
}else {
    echo 'Apollo配置更新完成' . PHP_EOL;
}
