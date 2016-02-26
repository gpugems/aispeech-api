# 概述 #
> 目前开发者调用API可能出现的错误有：Flash组件错误,录音服务器错误和内核计算错误。

  1. 内核错误码 (0 - 39999)
    * 20001 VAD模块没有检测到语音端点 Speech server detected no start of the speech, please try again.
    * 20002 输入VAD模块的Package数据为空 Speech server detected no start of the speech, please try again.
    * 20101 提取的所有F0特征均为0 Speech server detected no speech, please try again.
    * 20102 经过特征后处理，没有得到voiced段 Speech server detected no speech, please try again.
    * 20300 识别模块一般性错误 Speech server detected incompleted speech, please try again.
    * 20301 当前不支持这个单词 this word is not supported right now, please skip this word.
    * 20303 切分没有结果,no token suvived Speech server cannot recognise the speech. Please try again.
    * 20302 没有识别结果, no token suvived Speech server cannot recognise the speech. Please try again.
    * 20401 信噪比过低 Speech is too weak to process, please try again.
    * 20402 语音能量过低 Speech is too weak to process, please try again.
    * 20403 语音能量过高 Speech is too laud to process, please try again.
    * 20404 出现截幅现象 Speech is too laud to process, please try again.
    * 503   计算超时， Speech Server Timeout, please try again.
    * others ， Speech server error. Please contact us to report this.
  1. RTMP Server 错误码 (40000 - 49999)
    * 40001 AUDIO\_FILE\_NOTEXSIT Media server error, please try again.
    * 40002 AUDIO\_FILE\_OPEN\_FAIL Media server error, please try again.
    * 40003 AUDIO\_CONVERT\_ERROR, convert flv to wav error Media server error, please try again.
    * 40004 AUDIO\_FILE\_EMPTY, file size <= 13 bytes Media server error, please try again.
    * 40031 PARAM\_MISMATCH, 参数不正确 Media server cannot recognise the parameter. Please contact us to report this.
    * 40051   Media server error, please try again.
  1. Flash组件错误码 (50000 - 59999)
    * 50000 FLASH\_LOAD\_COMPLETE flash load complete
    * 50001 MIC\_UNMUTED microphone is unmuted
    * 50002 MIC\_MUTED microphone is muted, please add the permission for microphone using
    * 50003 MIC\_NOT\_FOUND please check the audio driver or try install latest flashplayer from adobe
    * 50004 FUNCTION\_EXECUTE\_SUCCESSFUL excute function successfully
    * 50100 FMS\_CONNECT\_SUCCESSFUL recorder server connect successful
    * 50101 FMS\_CONNECT\_FAILED recorder server connect failed
    * 50102 FMS\_CONNECT\_REJECTED recorder server connect rejected
    * 50103 FMS\_CONNECT\_CLOSED recorder server connect closed
    * 50104 FMS\_CONNECT\_TIMEOUT recorder server connect timeout
    * 50105 FMS\_CONNECT\_NET\_CHANGE recorder server connect net change, 这个只能作为状态报告用，比如出现用户网口硬件断开，或者硬件网络端口连上了
    * 50106 EXCEPTION\_FMS\_DISCONNECTED recorder server not connected
    * 50108 ASPING\_DETECT\_STATUS bwcheck status info
    * 50200 CORE\_REQUEST\_GETTED get core request
    * 50201 CORE\_REQUEST\_TIMEOUT get core request timeout
    * 50300 RECORD\_STOP recorder record stop
    * 50301 RECORD\_START recorder record start
    * 50302 REPLAY\_STOP recorder replay stop
    * 50303 REPLAY\_START recorder replay start
    * 50304 RECORDID\_GETTED get recordId
    * 50351 ERROR\_STARTRECORD\_PARAMETER\_ERROR recorder startRecord parameter error
    * 50352 ERROR\_STARTREPLAY\_PARAMETER\_ERROR recorder startReplay parameter error
    * 50353 ERROR\_RECORDER\_STATUS\_ERROR recorder status error
      * "status.invalid:recording"
      * "status.invalid:idle"
      * "status.invalid:replaying"
      * "status.invalid:not\_ready"
      * "status.invalid:torecord"
      * "status.invalid:init"
    * 50400 PLAYER\_AUDIO\_LOAD\_COMPLETED player audio load complete
    * 50401 PLAY\_START player play start
    * 50402 PLAY\_STOP player play stop
    * 50403 PLAY\_BUFFERING player audio buffering
    * 50404 PLAY\_CONTINUE player audio 从 buffering 恢复播放
    * 50405 PLAY\_PAUSE player play pause
    * 50406 PLAY\_RESUME player play resume
    * 50407 PLAY\_SEEK\_SUCCESSFUL player seek successful
    * 50408 PLAY\_SEEK\_FAILED player seek failed
    * 50409 PLAY\_FILE\_NOT\_FOUND player not found file
    * 50410 PLAY\_SERVER\_ERROR player server error
    * 50411 PLAY\_NETSTREAM\_INSUFFICIENT\_BW  客户端没有足够的带宽，无法以正常速度播放数据
    * 50412 PLAYER\_AUDIO\_LOAD\_FAILED player audio load failed
    * 50413PLAYER\_FILE\_NOT\_LOADED player audio not loaded
    * 50450 ERROR\_STARTPLAY\_PARAMETER\_ERROR player startPlay parameter error
    * 50451 ERROR\_LOADAUDIO\_PARAMETER\_ERROR player loadAudio parameter error
    * 50452 ERROR\_ADJUSTVOLUME\_PARAMETER\_ERROR player adjustVolume parameter error
    * 50453 ERROR\_PLAYER\_FLASHVARS\_ERROR player flashvars error
    * 50454 ERROR\_PLAYER\_STATUS\_ERROR player status error
      * "status.invalid:idle"
      * "status.invalid:playing"
      * "status.invalid:loading"
      * "status.invalid:pause"
      * "status.invalid:buffering"
      * "status.invalid:loaded"