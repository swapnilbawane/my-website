---
sidebar_position: 7
---

# Modal - Chakra UI lib

## Installation

To use Chakra UI in your project, run one of the following commands in your terminal:

`npm i @chakra-ui/react @emotion/react @emotion/styled framer-motion`

## Setup
After installing Chakra UI, you need to set up the ChakraProvider at the root of your application. This can be either in your index.jsx, index.tsx or App.jsx depending on the framework you use.

```javascript title="App.jsx"
import * as React from "react";

// 1. import `ChakraProvider` component
import { ChakraProvider } from "@chakra-ui/react";

function App() {
  // 2. Wrap ChakraProvider at the root of your app
  return (
    <ChakraProvider>
      <TheRestOfYourApplication />
    </ChakraProvider>
  );
}
```

## Modal application

```javascript title="MainProfile.jsx"
import {
  Modal,
  ModalOverlay,
  ModalContent,
  ModalHeader,
  ModalFooter,
  ModalBody,
  ModalCloseButton,
} from "@chakra-ui/react";

import { Button } from "@chakra-ui/react";

export function MainProfile() {
  const [isModalOpen, setIsModalOpen] = useState(false);

  const handleProfileEditClick = () => {
    setIsModalOpen(true);
  };

  const handleCloseModal = () => {
    setIsModalOpen(false);
  };

  return (
    <>
      <button
        className="border lynx-white-bg p-xs m-xs fw-semibold width-8"
        onClick={handleProfileEditClick}
      >
        Edit Profile Details
      </button>

      <Modal isOpen={isModalOpen} onClose={handleCloseModal}>
        <ModalOverlay />
        <ModalContent>
          <ModalHeader>Your Profile Details</ModalHeader>
          <ModalCloseButton />
          <ModalBody>
            <div className="editprofile-container">
              <div className="gravatar-body">
                <div>
                  <p> Change your Gravatar </p> // title
                </div>

                <div className="gravatar-container">
                  <img
                    src="https://res.cloudinary.com/djhnar3ju/image/upload/v1688106576/Gravatar/Gravatar_2.jpg"
                    alt="gravatar_1"
                    name="gr_1"
                    className="gravatar-icon"
                    onClick={() =>
                      avatarHandler(
                        "https://res.cloudinary.com/djhnar3ju/image/upload/v1688106576/Gravatar/Gravatar_2.jpg"
                      )
                    }
                  />

                  <img
                    src="https://res.cloudinary.com/djhnar3ju/image/upload/v1688106577/Gravatar/Gravatar_3.jpg"
                    alt="gravatar_1"
                    name="gr_2"
                    className="gravatar-icon"
                    onClick={() =>
                      avatarHandler(
                        "https://res.cloudinary.com/djhnar3ju/image/upload/v1688106577/Gravatar/Gravatar_3.jpg"
                      )
                    }
                  />

                  <img
                    src="https://res.cloudinary.com/djhnar3ju/image/upload/v1688106576/Gravatar/Gravatar_4.jpg"
                    alt="gravatar_1"
                    name="gr_3"
                    className="gravatar-icon"
                    onClick={() =>
                      avatarHandler(
                        "https://res.cloudinary.com/djhnar3ju/image/upload/v1688106576/Gravatar/Gravatar_4.jpg"
                      )
                    }
                  />

                  <img
                    src="https://res.cloudinary.com/djhnar3ju/image/upload/v1688106576/Gravatar/Gravatar_5.jpg"
                    alt="gravatar_1"
                    name="gr_4"
                    className="gravatar-icon"
                    onClick={() =>
                      avatarHandler(
                        "https://res.cloudinary.com/djhnar3ju/image/upload/v1688106576/Gravatar/Gravatar_5.jpg"
                      )
                    }
                  />

                  <img
                    src="https://res.cloudinary.com/djhnar3ju/image/upload/v1688106576/Gravatar/Gravatar_6.jpg"
                    alt="gravatar_1"
                    name="gr_5"
                    className="gravatar-icon"
                    onClick={() =>
                      avatarHandler(
                        "https://res.cloudinary.com/djhnar3ju/image/upload/v1688106576/Gravatar/Gravatar_6.jpg"
                      )
                    }
                  />

                  <img
                    src="https://res.cloudinary.com/djhnar3ju/image/upload/v1688107497/Gravatar/Gravatar_1.jpg"
                    alt="gravatar_1"
                    name="gr_6"
                    className="gravatar-icon"
                    onClick={() =>
                      avatarHandler(
                        "https://res.cloudinary.com/djhnar3ju/image/upload/v1688107497/Gravatar/Gravatar_1.jpg"
                      )
                    }
                  />
                </div>

                <hr />

                <div className="current-gravatar">
                  <p> Your gravatar </p>
                  <img
                    src={textEdit.profileimage}
                    alt="gravatar_1"
                    className="gravatar-icon"
                  />
                </div>
              </div>

              <hr />

              <p>
                Name: {currentUser.firstName} {currentUser.lastName}
              </p>
              <hr />
              <p> Username: {currentUser.username} </p>
              <hr />
              <br />
              <p> Bio </p>
              <textarea
                name="bio"
                value={textEdit.bio}
                onChange={textEditHandler}
              >
                {currentUser.bio}
              </textarea>

              <hr />
              <br />
              <p> Link ( eg. https://www.example.com ) </p>
              <textarea
                name="link"
                value={textEdit.link}
                onChange={textEditHandler}
              >
                {currentUser.link}
              </textarea>
            </div>
          </ModalBody>
          <ModalFooter>
            <Button
              colorScheme="blue"
              mr={3}
              onClick={() => {
                editUserHandler(textEdit);
                handleCloseModal();
              }}
            >
              Save
            </Button>
            {/* <Button variant="ghost">Delete</Button> */}
          </ModalFooter>
        </ModalContent>
      </Modal>
    </>
  );
}
```
## Modal demo 

## Edit Profile Page 
![7_EditProfile_1](https://github.com/swapnilbawane/sm-app-v1/assets/90078330/473cd704-4a97-48c9-aa6c-cf65b418f3d9)

![7_EditProfile_2](https://github.com/swapnilbawane/sm-app-v1/assets/90078330/7d4c4643-f357-4f44-96d3-50ecb4365f2b)

![8_EditProfile_Updated](https://github.com/swapnilbawane/sm-app-v1/assets/90078330/3bfbb082-e589-4b7e-bd09-4e18414af5ba)

