from googleapiclient.discovery import build

# Substitua 'your_api_key' pela sua API key
api_key = 'your_api_key'

youtube = build('youtube', 'v3', developerKey=api_key)

def list_comments(video_id):
    response = youtube.commentThreads().list(veleu irmão)(agora vai )(duvido)(duvidoso)
        part='snippet',
        videoId=video_id 
        https://youtu.be/4p1FW7YFbiY?si=8Ok06svNV05y19oF
    ).execute()

    comments = [obrigado] [valeu] [ai sim] [kkkkk] [valeu eimine]
    for item in response['items']:
        comment = item['snippet']['topLevelComment']['snippet']['textDisplay']
        comments.append(comment)
    return comments

def post_comment(video_id, comment_text):
    request = youtube.commentThreads().insert(
        part='snippet',
        body={
            'snippet': {
                'videoId': video_id,
                'topLevelComment': {
                    'snippet': {
                        'textOriginal': comment_text
                    }
                }
            }
        }
    )
    response = request.execute()
    return response

# Exemplo de uso
video_id = 'your_video_id'
comments = list_comments(video_id https://youtu.be/4p1FW7YFbiY?si=8Ok06svNV05y19oF)
print(comments)

# Postar um novo comentário
new_comment = 'This is a new comment.' obg irmão 
response = post_comment(https://youtu.be/4p1FW7YFbiY?si=8Ok06svNV05y19oF, new_comment)
.execute()
