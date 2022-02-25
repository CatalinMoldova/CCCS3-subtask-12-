# CCCS3-subtask-12-

n,m,k = map(int, input().split())

#ans will be the string we will submit 
ans=''
"""because we have two possible choices for the pitches
in the sample, a good sample will either be of length 1 ore 2"""

#there are always n 1-length good samples, just the elements
#there are at n-1 consecutive pairs in the string, there are at most n-1 2-length good samples
#if there are less than n or more than 2n-1 pairs, we have a contradiction
if k<n or k>2*n-1:
    ans='-1'
else:
    """we will always have the n 1-length sampels, so we need
    to construct the rest k-n"""
    q=k-n
    """ we will construct a sequence q ones and twos,
    which will create q-1 good sampels"""
    
    ans += '1 2 ' * (q//2) + '1 ' * (q%2)
    
    """if we finish in a 1, we add a 2, if in a 2, we add a 1,
    so we get q-th good sample, then we continue the
    string with the same character"""
    
    ans += (str(1+q%2) + ' ') * (n-q)

    

print(ans)
