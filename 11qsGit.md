
# 11 câu hỏi đau đớn về git sẽ khiến bạn phát khóc

### Q1: Git fork là gì? Sự khác biệt fork, branch và clone là gì?

> Topic: **Git**  
Difficulty: ⭐⭐

  * Một **fork**  là một bản sao remote, phía server của một repository, tách bạch với bản gốc. Fork không thực sự là một khái niệm của  Git, nó giống một ý tưởng chính trị / xã hội hơn.
  * Một **clone** không phải là một fork; một clone là một bản sao dưới local của một remote repository. Khi bạn clone, thực ra là bạn đang sao chép toàn bộ source repository, bao gồm tất cả lịch sử và các nhánh.
  * Một **branch** là một cơ chế để xử lý các thay đổi trong một repo duy nhất để cuối cùng merge chúng với phần còn lại của code . Một branch là một phần của một repository. Về mặt khái niệm, nó đại diện cho một luồng phát triển.

**Source:** [stackoverflow.com](https://stackoverflow.com/questions/3329943/git-branch-fork-fetch-merge-rebase-and-clone-what-are-the-differences/)

### Q2: Điểm khác biệt giữa "pull request" và "branch"?

> Topic: **Git**  
Difficulty: ⭐⭐

  * A **branch** chỉ là một phiên bản của code  

  * A **pull request** là khi ai đó lấy repository, tạo nhánh của riêng họ, thực hiện một số thay đổi, sau đó cố gắng merge nhánh đó vào (đưa thay đổi của họ vào repo code của người khác).  


**Source:** [stackoverflow.com](https://stackoverflow.com/questions/19059838/whats-the-difference-between-a-pull-request-and-a-branch)

### Q3: Khác biệt giữa "git pull" và "git fetch"?

> Topic: **Git**  
Difficulty: ⭐⭐

Hiểu ngắn gọn, `git pull` thực hiện một `git fetch` theo sau là một `git
merge`.  

  * Khi bạn sử dụng `pull`, Git sẽ cố gắng tự động thực hiện công việc cho bạn. **Tùy vào hoàn cảnh**, Git sẽ merge mọi commit được pull vào nhánh bạn đang làm việc. `pull` **tự động gộp các commit mà bạn bạn không cần xem chúng trước**. Nếu bạn không quản lý chặt chẽ các nhánh của mình, bạn có thể thường xuyên gặp phải xung đột.    

  * Khi bạn `fetch`, Git sẽ tập hợp các commit từ nhánh chỉ định mà không có trong branch hiện tại của bạn và **lưu nó trong repository trên local của bạn**. Tuy nhiên, **nó không merge chúng với nhánh hiện tại của bạn**. Điều này đặc biệt hữu ích nếu bạn cần cập nhật repository của bạn, nhưng những thứ đang làm việc có thể bị hỏng nếu bạn cập nhật các file của mình. Để tích hợp các commit vào nhánh master của bạn, bạn sử dụng `merge`.  

**Source:** [stackoverflow.com](https://stackoverflow.com/questions/292357/what-is-the-difference-between-git-pull-and-git-fetch)

### Q4: Làm sao để quay lại lần commit trước trong git?

> Topic: **Git**  
Difficulty: ⭐⭐⭐

Giả sử bạn có điều này, trong đó C là con trỏ HEAD của bạn và (F) là trạng thái file của bạn.

  * Để nuke thay đổi trong commit: 

Bây giờ B là HEAD. Bởi vì bạn đã sử dụng --hard, các file của bạn được reset về trạng thái ở commit B  

  * undo nhưng vẫn giữ thay đổi:

Now we tell Git to move the HEAD pointer back one commit (B) and leave the
files as they are and `git status` shows the changes you had checked into C.

  * To undo your commit but leave your files and your index

Khi bạn thực hiện `git status`,bạn sẽ thấy các file cùng với index như trước đó.

**Source:** [stackoverflow.com](https://stackoverflow.com/questions/927358/how-to-undo-the-most-recent-commits-in-git)

### Q5: "git cherry-pick" là gì?

> Topic: **Git**  
Difficulty: ⭐⭐⭐

Câu lệnh git _cherry-pick_ thường được dùng để chỉ các commit cụ thể từ một branch trong một repository trên một branch khác. Thường được sử dụng để chuyển tiếp hoặc back-port các commit từ nhánh bảo trì đến nhánh phát triển.  


Điều này tương phản với các cách khác như merge và rebase thường thì chấp nhận nhiều commit trên một nhánh khác.

Ví dụ:

    
    
    git cherry-pick <commit-hash>
    

**Source:** [stackoverflow.com](https://stackoverflow.com/questions/9339429/what-does-cherry-picking-a-commit-with-git-mean)

### Q6: Giải thích những ưu điểm của Forking Workflow

> Topic: **Git**  
Difficulty: ⭐⭐⭐

**Forking Workflow** về cơ bản sẽ khác với các luồng làm việc Git khác. Thay vì sử dụng một repository duy nhất phia server để hoạt động như một
"trung tâm" codebase, nó cung cấp cho mỗi developer một repository phía server riêng của họ. "Forking Workflow" thường thấy nhất trong các dự án open soure công khai.  

Ưu điểm chính của Forking Workflow là các đóng góp có thể được tích hợp mà không cần mọi người push vào một repository trung tâm duy nhất giúp lịch sử commit của dự án được sạch sẽ. Các developer sẽ push lên các repository phía server của họ, và chỉ người bảo trì dự án có thể push lên repository chính.  

Khi các developer sẵn sàng publish một commit local, họ push commit đó lên repository công khai của họ, không phải là repository chính. Sau đó, họ tạo một pull request tới repository chính, cho phép người bảo trì dự án biết rằng bản cập nhật sẵn sàng được tích hợp.  


**Source:** [atlassian.com](https://www.atlassian.com/git/tutorials/comparing-workflows/forking-workflow)

### Q7: Khác biệt giữa HEAD, working tree và index, trong Git?

> Topic: **Git**  
Difficulty: ⭐⭐⭐

  * The **working tree/working directory/workspace** là cây thư mục (mã nguồn) của các file mà bạn có thể nhìn thấy và chỉnh sửa.  
  * The **index/staging area** là các file đơn lẻ , lớn, file nhị phân trong /,git/index , liệt kê tất cả các file ở trong nhánh hiện tại , check tổng sha1 , thời gian và tên file - nó không phải là thư mục khác với các bản sao file trong đó.  


  * **HEAD** là một tham chiếu đến commit cuối cùng trên check-out nhánh hiện tại.

**Source:** [stackoverflow.com](https://stackoverflow.com/questions/3689838/whats-the-difference-between-head-working-tree-and-index-in-git)

### Q8: Giải thích Gitflow workflow?

> Topic: **Git**  
Difficulty: ⭐⭐⭐

Gitflow workflow (luồng làm việc) sử dụng hai nhánh _long running_ để lưu lịch sử của project là `master` và `develop`:  

  * **Master** \- luôn sẵn sàng để được phát hành trên LIVE, với mọi thứ được kiểm tra và  phê duyệt đầy đủ (sẵn sàng cho production).  

    * **Hotfix** \-  nhánh bảo trì hay 'hotfix' được sử dụng để nhanh chóng phát hành trong bản vá. Nhánh Hotfix rất giống với nhánh release và nhánh feature ngoại trừ việc chúng dựa trên `master` thay vì `develop`.
  

  * **Develop** \- là nhánh mà tất cả các nhánh tính năng merge vào và nơi tất cả các test được thực hiện. Chỉ khi mọi thứ được kiểm tra kỹ lưỡng và sửa thì nó mới có thể được merge với `master` 

    * **Feature** \- mỗi tính năng mới nên được để ở trong nhánh riêng của nó, nó có thể được push lên nhánh `develop` giống nhánh cha của chúng.  

[![Gitflow workflow](https://res.cloudinary.com/practicaldev/image/fetch/s--
pLQxGakq--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://wac-cdn.
atlassian.com/dam/jcr:61ccc620-5249-4338-be66-94d563f2843c/05%2520%282%29.svg%
3FcdnVersion%3Dji)](https://res.cloudinary.com/practicaldev/image/fetch/s--
pLQxGakq--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://wac-cdn.
atlassian.com/dam/jcr:61ccc620-5249-4338-be66-94d563f2843c/05%2520%282%29.svg%
3FcdnVersion%3Dji)

**Source:** [atlassian.com](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)

### Q9: Khi nào tôi nên sử dụng "git stash"?


> Topic: **Git**  
Difficulty: ⭐⭐⭐

Câu lệnh `git stash` lấy tất cả những thay đổi uncommited của bạn (bao gồm cả staged và unstaged) , lưu chúng để sử dụng sau này , và sau đó phục hồi chúng từ bản sao làm việc của bạn.

Consider:

    
    
    $ git status
    On branch master
    Changes to be committed:
    new file: style.css
    Changes not staged for commit:
    modified: index.html
    $ git stash
    Saved working directory and index state WIP on master: 5002d47 our new homepage
    HEAD is now at 5002d47 our new homepage
    $ git status
    On branch master
    nothing to commit, working tree clean
    

Chúng ta có thể sử dụng stash khi chúng ta phát hiện ra chúng ta đã quên điều gì đó trong
commit cuối cùng và đã bắt đầu làm việc tiếp theo trên nhánh đó:  

    
    
    # Assume the latest commit was already done
    # start working on the next patch, and discovered I was missing something # stash away the current mess I made
    $ git stash save # some changes in the working dir # and now add them to the last commit:
    $ git add -u
    $ git commit --ammend # back to work!
    $ git stash pop
    

**Source:** [atlassian.com](https://www.atlassian.com/git/tutorials/saving-changes/git-stash)

### Q10: Làm thế nào để xóa một file khỏi git mà không cần xóa nó trong hệ thống file của bạn?
system?

> Topic: **Git**  
Difficulty: ⭐⭐⭐⭐

Nếu bạn không cẩn thận trong việc dùng `git add` , bạn sẽ thêm những file mà bạn không hề muốn commit. Tuy nhiên, `git rm` sẽ xóa nó khỏi cả hai vùng stage (chỉ mục), cũng như hệ thống file của bạn (working tree), có thể
không phải là những gì bạn muốn.  

Thay vào đó dùng `git reset`:

    
    
    git reset filename # or
    echo filename >> .gitingore # add it to .gitignore to avoid re-adding it
    

Điều này có nghĩa là `git reset <paths>` trái ngược với `git add <paths>`.

**Source:** [codementor.io](https://www.codementor.io/citizen428/git-tutorial-10-common-git-problems-and-how-to-fix-them-aajv0katd)

### Q11: Khi nào thì dùng "git rebase" thay vì "git merge"?


> Topic: **Git**  
Difficulty: ⭐⭐⭐⭐⭐

Cả 2 câu lệnh trên đều được tạo ra để tích hợp những thay đổi từ một nhánh vào nhánh khác - chúng làm việc đó theo nhiều cách khác nhau.

Trước khi merge/rebase:

    
    
    A <- B <- C [master]
    ^ \ D <- E [branch]
    

sau `git merge master`:

    
    
    A <- B <- C
    ^ ^ \ \ D <- E <- F
    

sau `git rebase master`:

Với rebase thì bạn đang sử dụng một nhánh làm base mới cho công việc của bạn.  

**Khi nào sử dụng:**  

  1. Nếu bạn bạn còn chưa chắc chắn, sử dụng merge.  
  2. Lựa chọn rebase hay merge tùy thuộc vào việc bạn muốn lịch sử trông như thế nào.  

**Các yếu tố cần xem xét:**

  1. **Nhánh của bạn có đang nhận được các thay đổi từ việc chia sẻ với các developer khác bên ngoài nhóm của bạn (ví dụ: opensource, public) không?** Nếu có, đừng rebase. Rebase phá hủy nhánh và các developer đó sẽ có các repository bị phá hỏng / không nhất quán trừ khi họ sử dụng `git pull --rebase`.  
  2. **Đội ngũ phát triển của bạn có kỹ năng như thế nào?** Rebase là một hành động mang tính phá hủy. Điều đó có nghĩa, nếu bạn không áp dụng nó một cách chính xác, bạn có thể mất các công việc đã commit và hoặc phá vỡ sự thống nhất giữa các repository của các developer.  
  3. **Bản thân nhánh đó có thể hiện thông tin hữu ích không?** Một số team sử dụng mô hình `branch-per-feature`  nơi mà mỗi nhánh thể hiện một tính năng (hoặc bugfix hoặc tính năng con, ...). Trong mô hình này nhánh giúp xác định tập các commit liên quan. Trong trường hợp mô hình `branch-per-developer` chính nhánh không truyền tải bất cứ thông tin bổ sung nào (commit đã lưu tác giả). Sẽ không có hại gì khi rebase  
  4. **Bạn có thể muốn revert một merge vì bất kỳ lý do nào?**  Revert (giống như undo) một rebase là một điều khá khó khăn và không thể (nếu rebase có xung đột) so với revert một merge. Nếu bạn nghĩ rằng có thể có một cơ hội bạn sẽ muốn revert thì sử dụng merge  

**Source:** [stackoverflow.com](https://stackoverflow.com/questions/804115/when-do-you-use-git-rebase-instead-of-git-merge)

> _Thanks  for reading and good luck on your interview!_  
_Check more FullStack Interview Questions &amp; Answers on
[www.fullstack.cafe](https://www.fullstack.cafe/)_
