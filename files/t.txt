var domains = {
    "google.com": 1,
    "facebook.com": 1,
    "admob.com": 1,
    "amazonaws.com": 1,
    "android.com": 1,
    "googleusercontent.com": 1,
    "googleblog.com": 1,
    "twitter.com": 1,
    "wikipedia.org": 1,
    "cybergrandchallenge.com": 1,
    "xys.org": 1,
    "googleapis.com": 1,
    "darpa.mil": 1,
    "dtic.mil": 1,
    "bluekai.com": 1,
    "golang.org": 1,
    "blogspot.com":1
};
 
var proxy = "PROXY 127.0.0.1:8080; DIRECT;";
 
var direct = 'DIRECT;';
 
function FindProxyForURL(url, host) {
    var lastPos;
    do {
        if (domains.hasOwnProperty(host)) {
            return proxy;
        }
        lastPos = host.indexOf('.') + 1;
        host = host.slice(lastPos);
    } while (lastPos >= 1);
    return direct;
}
