# 微信公众号服务端 for handsome主题

## 使用方法

[查看搭建教程](https://ifking.cn/p/113.html)

## 微信公众号服务端 for handsome主题
## *本项目需要配合handsome主题的时光机使用*


## 主要是修改cross.php这个文件,在GitHub下载会乱码,导致无法正常md5加密
function push($content, $msg_type, $url, $timecode, $cid, $mid)
{
    $desp = array('cid' => $cid, 'mid' => $mid, 'content' => $content, 'action' => "send_talk", 'time_code' =>md5($timecode), 'msg_type' => $msg_type, 'token' => 'weixin');
    $res = request_post($url, $desp);
    return $res;
}
