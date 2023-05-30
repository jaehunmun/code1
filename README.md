# Progranmmers
# # 12948번
# def solution(phone_number):
#     print((len(phone_number)-4)*"*" + phone_number[-4:])
#     return

# # 12947번
# def solution(x):
#     digit_sum = sum([int(i) for i in str(x)])
#     if x % digit_sum == 0:
#         return True
#     return False
#
# def solution(x):
#     a = 0
#     copy = x #밑 과정에서 X값이 0이 되기 때문에 x의 복사본을 만들어야한다.
#     while x:
#         a += x % 10
#         x //= 10
#     return copy % a == 0
#
# x = 10
# print(solution(x))

# def solution(n, lost, reserve):
#     students = [1] * n
#     for x in lost:
#         students[x-1] -= 1
#     for y in reserve:
#         students[y-1] += 1
#
#     for i in range(n):
#         if students[i] == 0:
#             if i > 0 and students[i-1] == 2:
#                 students[i] += 1
#                 students[i-1] -= 1
#             elif i+1 < len(students) and students[i+1] == 2:
#                 students[i] += 1
#                 students[i+1] -= 1
#     p = 0
#     for s in students:
#         if s >= 1:
#             p += 1
#     return p
#
#
# n = 5
# lost = [2,4]
# reserve = [1,3,5]
# print(solution(n,lost,reserve))


# def solution(s):
#     if len(s) == 4 or len(s) == 6:
#         if s.isnumeric():
#             return True
#         return False
#     return False
#
# print(solution("a123"))

# # 12950 번
# def solution(arr1, arr2):
#     answer = []
#     for i in range(len(arr1)):
#         inner = []
#         answer.append(inner)
#         for j in range(len(arr1[i])):
#             inner.append(arr1[i][j] + arr2[i][j])
#
#     return answer

# # 12969 번
# col, row = map(int, input().strip().split(' '))
#
# line =  col * "*"
# for i in range(row):
#     print(line)

# # 12940 번
# import math
# def solution(n, m):
#     gcd = math.gcd(n, m)
#     return [gcd,n*m // gcd]

# # 12906 번
# def solution(arr):
#     sol = []
#     for i in range(len(arr)):
#         if i + 1 < len(arr) and arr[i] == arr[i+1]:
#             continue
#         else:
#             sol.append(arr[i])
#     return sol

# # 68935 번
# def solution(n):
#     ternery = ""
#     while n > 0:
#         ternery += str(n % 3)
#         n = n // 3
#     return int(ternery, 3)

# # 12930 번
# def solution(s):
#     answer = []
#     for i in s.split(" "):
#         sol = ""
#         for j in range(len(i)):
#             if j % 2 == 0:
#                 sol += i[j].upper()
#             else:
#                 sol += i[j].lower()
#         answer.append(sol)
#     return " ".join(answer)
#
# print(solution("try Hello world Myname South Korea"))

# # 17681 번
# def binary(n, number):
#     answer = ""
#     while number:
#         answer += str(number % 2)
#         number //= 2
#     answer = answer[::-1]
#     while len(answer) < n:
#         answer = "0" + answer
#     return answer
#
#
# def solution(n,arr1,arr2):
#     map1 = []
#     map2 = []
#     answer = []
#     for i in range(n):
#         map1.append(binary(n,arr1[i]))
#         map2.append(binary(n,arr2[i]))
#
#     for i in range(n):
#         string = ''
#         for j in range(n):
#             if map1[i][j] == '0' and map2[i][j] == '0':
#                 string += " "
#             else:
#                 string += "#"
#         answer.append(string)
#     return answer
#
# n = 5
# arr1 = [9, 20, 28, 18, 11]
# arr2 = 	[30, 1, 21, 17, 28]
# # ["#####","# # #", "### #", "# ##", "#####"]
# print(solution(n,arr1,arr2))

# # 12982 번
# def solution(d, budget):
#     dsort = sorted(d)
#     cnt = 0
#     for i in range(len(dsort)):
#         cnt += 1
#         budget -= dsort[i]
#         if budget < 0:
#             cnt -= 1
#             break
#     return cnt
#
# d = [2,2,3,3]
# budget = 10
# print(solution(d, budget))

# 12926 번
# def solution(s, n):
#     up_alp = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
#     low_alp = 'abcdefghijklmnopqrstuvwxyz'
#     answer = ""
#     for i in range(len(s)):
#         if not s[i] == " ":
#             if s[i].islower():
#                 for j in range(len(low_alp)):
#                     if s[i] == low_alp[j]:
#                         answer += low_alp[(j+n) % 26]
#             else:
#                 for k in range(len(up_alp)):
#                     if s[i] == up_alp[k]:
#                         answer += up_alp[(k+n) % 26]
#         else:
#             answer += " "
#     return answer
# s="a B z"
# n= 4
# print(solution(s,n))

# def solution(s, n):
#     alphabet = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
#     answer = ''
#     for i in s:
#         if i.isalpha(): #i가 알파벳이냐
#             if i.isupper(): #i가 대문자냐
#                 idx = (alphabet.find(i) + n) % 26
#                 answer += alphabet[idx]
#             else: #i가 소문자냐
#                 temp = i.upper()
#                 idx = (alphabet.find(temp) + n) % 26
#                 answer += alphabet[idx].lower()
#
#
#         else:
#             answer += i
#     return answer
#
# s="a B z"
# n= 4
# print(solution(s,n))

# 131705 번
# def solution(number):
#     answer = 0

# 12981 번
# def solution(n, words):
#     cnt = 0
#     for i in range(len(words)):
#         if words[i] in words[:i]:
#             if words[i][0] != words[i-1][-1]:
#                 cnt = i
#                 break
#         else:
#             break
#
#     answer = [cnt % n + 1, cnt // n + 1]


# def solution(n, words):
#     answer = [0,0]
#     for i in range(1,len(words)):
#         if words[i] in words[:i]:
#             answer = [i % n +1, i//n + 1]
#             break
#         elif words[i-1][-1] != words[i][0]:
#             answer = [i % n +1, i//n + 1]
#             break
#         elif len(words[i]) == 1:
#             answer = [i % n +1, i//n + 1]
#             break
#     return answer
#
# n = 3
# words = ["tank", "kick", "know", "wheel", "land", "dream", "mother", "robot", "tank"]
# print(solution(n,words))


# # 131705 번
# def solution(number):
#     answer = 0
#     for i in range(len(number)):
#         for j in range(i+1,len(number)):
#             for k in range(j+1,len(number)):
#                 if number[i] + number[j] + number[k] == 0:
#                     answer += 1
#     return answer


#
#
#
# number = [-2, 3, 0, 2, -5]
# print(solution(number))
#
# # 93234번
# def solution(id_list, report, k):
#     # report = ['신고한사람 신고당한 사람']
#     # id_list 순서대로 메일을 받은 횟수를 return 하시오.
#     # 메일은 유저가 k번이상 신고 당했을 때 자신을 신고한 사람들에게 보낸다.
#     # 한 사람이 같은 사람을 여러번 신고하면 신고 횟수는 1번으로 찬다
#     report_dict = {}
#     for names in report:
#         a, b = names.split()
#         if b not in report_dict:
#             report_dict[b] = [a]
#         else:
#             if a not in report_dict[b]:
#                 report_dict[b].append(a)
#
#     mail = [0]*len(id_list)
#
#     for value in report_dict.values():
#         if len(value) >= k:
#             for v in value:
#                 idx = id_list.index(v)
#                 mail[idx] += 1
#
#     return mail
#
#
#
#
#
# id_list = ["muzi", "frodo", "apeach", "neo"]
# report = ["muzi frodo","apeach frodo","frodo neo","muzi neo","apeach muzi"]
# k = 2
# print(solution(id_list,report,k))


# # 67256 번
# 멘해튼 방식으로 풀기
# def howfar(pos_l, pos_r, idx):
#     pos = [1, idx]
#     diff_pos_l = [pos[0] - pos_l[0], pos[-1] - pos_l[-1]]
#     diff_pos_r = [pos[0] - pos_r[0], pos[-1] - pos_r[-1]]
#     len_l = (diff_pos_l[0] ** 2 + diff_pos_l[-1] ** 2) ** (1 / 2)
#     len_r = (diff_pos_r[0] ** 2 + diff_pos_r[-1] ** 2) ** (1 / 2)
#
#     if len_l < len_r:
#         return "left"
#     elif len_l > len_r:
#         return "right"
#     else:
#         return "same"
#
#
# def solution(numbers, hand):
#     keypad = [[7, 4, 1], [0, 8, 5, 2], [9, 6, 3]]
#     answer = ""
#     pos_l = [0, 0]
#     pos_r = [2, 0]
#     for number in numbers:
#         if number in keypad[0]:
#             answer += "L"
#             pos_l[0],pos_l[-1] = 0, keypad[0].index(number) + 1
#             continue
#         elif number in keypad[-1]:
#             answer += "R"
#             pos_r[0], pos_r[-1] = 2, keypad[-1].index(number) + 1
#             continue
#         elif number in keypad[1]:
#             idx = keypad[1].index(number)
#             if howfar(pos_l, pos_r, idx) == "left":
#                 answer += "L"
#                 pos_l[0], pos_l[-1] = 1, idx
#                 continue
#             elif howfar(pos_l, pos_r, idx) == "right":
#                 answer += "R"
#                 pos_r[0], pos_r[-1] = 1, idx
#                 continue
#             else:
#                 answer += hand[0].upper()
#                 continue
#
#     return answer
#
#
# numbers = [1, 3, 4, 5, 8, 2, 1, 4, 5, 9, 5]
# hand = "right"

# # print(solution(numbers,hand))
# arr = []
# for i in range(1,n+1):
#     temp = []
#     for j in range(1,n+1):
#         temp.append(max(i,j))
#     arr.append(temp)
#
# arr2 =[]
# for a in arr:
#     arr2 += a
#
# print(arr)
#
# n = 4
# left = 7
# right = 14
# def solution(n, left, right):
#     arr = []
#     for i in range(1, n + 1):
#         temp = []
#         for j in range(1, n + 1):
#             temp.append(max(i, j))
#         arr.append(temp)
#
#     arr2 = []
#     for a in arr:
#         arr2 += a
#
#     return arr2[left:right+1]
#
# print(solution(n, left, right))


# coord = [0,0]
# answer = []
# for i in range(left, right +1):
#     coord[0], coord[1] = i // n, i % n
#     answer.append(max(coord) + 1)
# print(answer)


# n=4
# left=7
# right=14
# def solution(n, left, right):
#     coord = [0, 0]
#     answer = []
#     for i in range(left, right + 1):
#         coord[0], coord[1] = i // n, i % n
#         answer.append(max(coord) + 1)
#     return answer
# 
# print(solution(n, left, right))
