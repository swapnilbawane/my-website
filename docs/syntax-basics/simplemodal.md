---
sidebar_position: 15
---

# Simple Modal

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

## Code 

```javascript title="Modal.jsx"
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
```

```javascript title="Modal.jsx"
export function SomeApp() {
  const [isModalOpen, setIsModalOpen] = useState(false);

  const handleStartModal = () => {
    setIsModalOpen(true);
  };

  const handleCloseModal = () => {
    setIsModalOpen(false);
  };

  return (
    <>
      <div className="classic-modal">
        <>
          <button className="button" onClick={handleStartModal}>
            Start Modal
          </button>

          <Modal isOpen={isModalOpen} onClose={handleCloseModal}>
            <ModalOverlay />
            <ModalContent>
              <ModalHeader>Your Profile Details</ModalHeader>
              <ModalCloseButton />
              <ModalBody>
                <div className="editprofile-container">
                  <p> I am in the Modal </p>
                </div>
              </ModalBody>
              <ModalFooter>
                <Button
                  colorScheme="blue"
                  mr={3}
                  onClick={() => {
                    // editUserHandler(textEdit);
                    handleCloseModal();
                  }}
                >
                  Save
                </Button>
                <Button
                  variant="ghost"
                  onClick={() => {
                    // editUserHandler(textEdit);
                    handleCloseModal();
                  }}
                >
                  Delete
                </Button>
              </ModalFooter>
            </ModalContent>
          </Modal>
        </>
      </div>
    </>
  );
}
```
