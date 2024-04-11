from googleapiclient.discovery import build

# Substitua 'your_api_key' pela sua API key
api_key = 'AIzaSyAXG2QbZR7nRj3JHlNAf4LIBCZU4BTjGE8'

youtube = build('youtube', 'v3', developerKey=api_key)

def list_comments(https://youtu.be/4p1FW7YFbiY?si=LDUmPVhzjvs0_qOi):
    response = youtube.commentThreads().list(
        part='snippet',
        videoId=video_id
    ).execute()

    comments = []
    for item in response['items']:
        comment = item['snippet']['topLevelComment']['snippet']['textDisplay']
        comments.append(comment)
    return comments

def post_comment(https://youtu.be/4p1FW7YFbiY?si=LDUmPVhzjvs0_qOi,valeu):
    request = youtube.commentThreads().insert(
        part='snippet',
        body={
            'snippet': {
                'videoId':https://youtu.be/4p1FW7YFbiY?si=LDUmPVhzjvs0_qOi,
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
video_id = 'https://youtu.be/4p1FW7YFbiY?si=LDUmPVhzjvs0_qOi'  # Substitua pelo ID do vídeo desejado
comments = list_comments(video_id)
print(comments)

# Postar um novo comentário
new_comment = 'This is a new comment.'  # Substitua pelo comentário desejado
response = post_comment(video_id, new_comment)
print(response)

