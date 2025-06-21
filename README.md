# TMUXER
- 22-jun-2025
- Dont know why ssh output not working, below is the code, we ran this on ec2 dnf cmd.
```py
from tmuxer import TmuxSession

cmd = "ssh -o StrictHostKeyChecking=no -i kingfisher-key.pem ec2-user@15.206.163.194 'sudo dnf install -y docker vim wget curl dnsutils net-tools unzip git tree tmux; sleep 2'"
t = TmuxSession()
rc, o = t.run(cmd, attach=True)
# rc, o = t.run(cmd)
print(o)
```
- Almost 3 out of 6 pages lost in the output.
- Tried to use capture output and wait for grep to find the sentinel and exit, it exits but still lost the output.
- Pipe-pane unable to write/flush everything into shm.
