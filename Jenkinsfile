pipeline 
{
	agent any

	stages 
	{
		stage("ssh setup") 
		{
			steps 
			{
				sh "ssh deama85@instance-2 << EOF"
			}
		}
		stage("setup_git_repo") 
		{
			steps 
			{
				sh "sudo apt update"
				sh "cd ~"
				sh "git clone [REPO_LINK]"
				sh "cd [folder]"
				sh "git pull"
			}
		}
		stage("pip_install") 
		{
			steps 
			{
				sh "sudo apt install python3-pip"
				sh "y"
			}
		}
		stage("install_and_activate_virtualenv") 
		{
			steps 
			{
				sh "sudo pip3 install virtualenv"
				sh "sudo python3 ~/.local/lib/python3.6/site-packages/virtualenv.py venv"
				sh ". ./venv/bin/activate"
			}
		}
		stage("install_pip_requirements") 
		{
			steps 
			{
				sh "sudo pip3 install -r requirements.txt"
			}
		}
		stage("run_pytest") 
		{
			steps 
			{
				sh "pytest"
			}
		}
		stage("EOF") 
		{
			steps 
			{
				sh "EOF"
			}
		}
	}
}