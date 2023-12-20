# Social-media
media
import requests

def get_github_user(username):
    url = f"https://api.github.com/users/{username}"
    response = requests.get(url)

    if response.status_code == 200:
        user_data = response.json()
        print(f"GitHub User: {user_data['login']}")
        print(f"Name: {user_data['name']}")
        print(f"Bio: {user_data['bio']}")
        print(f"Public Repositories: {user_data['public_repos']}")
    else:
        print(f"Failed to retrieve user data. Status code: {response.status_code}")

if __name__ == "__main__":
    github_username = input("Enter GitHub username: ")
    get_github_user(github_username)
