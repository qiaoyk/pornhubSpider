# pornhun爬虫
可以获取pornhub的视频信息
## getVideoList 任意页面的视频列表
传入一个url如 www.pornhub.com/video?c=111&page=1<br>
该函数会返回一个字典，格式如下：
{
	{
    'title':'田川祐夢 c930',        #视频标题
    'preview' : 'https://xxxxxxx', #视频预览片段
    'pic' : 'https://xxxxxxx',     #视频封面
    'url' : 'https://xxxxxxx',     #视频播放地址
    'time' : 20.00                 #视频时长
    }，
    ...
}

## getVideoUrl 视频的全部清晰度下载地址及视频ID
传入视频播放地址，可解析出视频全部清晰度及视频ID（ID用于获取相似推荐），
返回值为列表，列表第一项为包含全部清晰度的字典，第二项为视频ID
例如：

[
	[{
			'defaultQuality': True,             #是否默认播放
			'format': 'mp4',                    #视频格式
			'quality': '720',                   #视频清晰度
			'videoUrl': 'https://xxxxxxx'       #视频地址（可直接用于下载）
	 },
	 ...
	 ],
	187765541                                   #视频ID
]
## getVideoSimilar 视频的全部相关推荐
传入视频ID,获取该视频ID的全部相似推荐（共60个），返回格式与getVideoList相同